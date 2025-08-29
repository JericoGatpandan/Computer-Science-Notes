
## 0) Preconditions

- You’re in your venv and the script runs (even with warnings) ✅
    
- Git is initialized.
    

```bash
cd "/home/jerico/Workspace/Machine Learning/stream_project"
git status
```

---

## 1) Create a safety branch + backup the monolith

```bash
git checkout -b refactor/modularize
cp Main.py monolith_backup.py
```

This keeps a working copy you can always diff/restore.

---

## 2) Snapshot current behavior (baseline)

Run once and note the key metrics & files the script produces (even if it crashes at JSON):

```bash
python Main.py | tee run_before_refactor.log
```

Record:

- KGE, NSE, CRPS, Coverage, Reliability
    
- Any generated PNGs
    
- The crash: `TypeError: Object of type int64 is not JSON serializable` (expected)
    

We’ll compare against these later.

---

## 3) Create the new module layout (empty files)

We’ll keep the package name `stream_project` and split the monolith into focused modules.

```bash
mkdir -p stream_project
touch stream_project/__init__.py
touch stream_project/logger.py
touch stream_project/errors.py
touch stream_project/config.py
touch stream_project/hydrology.py
touch stream_project/rainfall.py
touch stream_project/lorenz.py
touch stream_project/operators.py
touch stream_project/metrics.py
touch stream_project/filters.py
touch stream_project/validation.py
touch stream_project/utils.py
touch stream_project/simulation.py
touch main.py
```

---

## 4) Add minimal utilities (JSON fix + headless plotting + logger)

**stream_project/utils.py**

```python
import json
import numpy as np
import matplotlib
import matplotlib.pyplot as plt
from typing import Any

def headless_setup():
    # Safe for servers/CI; avoids "FigureCanvasAgg is non-interactive" noise
    matplotlib.use("Agg")

def save_figure(fig, path: str, dpi: int = 300, tight: bool = True):
    if tight:
        fig.tight_layout()
    fig.savefig(path, dpi=dpi, bbox_inches="tight")
    plt.close(fig)  # free memory

def _to_native(obj: Any):
    """Recursively convert numpy types to JSON-safe Python types."""
    if isinstance(obj, np.generic):
        return obj.item()
    if isinstance(obj, np.ndarray):
        return obj.tolist()
    if isinstance(obj, (list, tuple)):
        return [_to_native(x) for x in obj]
    if isinstance(obj, dict):
        return {k: _to_native(v) for k, v in obj.items()}
    return obj

def safe_json_dump(obj: Any, path: str, *, indent: int = 2) -> None:
    with open(path, "w") as f:
        json.dump(_to_native(obj), f, indent=indent, ensure_ascii=False)
```

**stream_project/logger.py**

```python
import logging

def get_logger(name: str = "stream_project"):
    logger = logging.getLogger(name)
    if not logger.handlers:
        logger.setLevel(logging.INFO)
        h = logging.StreamHandler()
        fmt = logging.Formatter("%(asctime)s - %(levelname)s - %(message)s")
        h.setFormatter(fmt)
        logger.addHandler(h)
        logger.propagate = False
    return logger

logger = get_logger()
```

**stream_project/errors.py**

```python
class ValidationError(Exception):
    """Raised for invalid configuration or inputs."""
    pass

class NumericalError(Exception):
    """Raised when numerical integration fails or becomes unstable."""
    pass
```

---

## 5) Move your existing code into modules (no logic changes)

Do **cut-paste** moves from `Main.py` into these files (names match what you showed in your IDE).

- **config.py** → move `@dataclass ModelParameters` exactly as-is.
    
- **errors.py** → keep `ValidationError`, `NumericalError` (remove duplicates from elsewhere).
    
- **rainfall.py** → `generate_physically_motivated_hyetograph`.
    
- **hydrology.py** → `scs_runoff_with_uncertainty`, `triangular_unit_hydrograph_enhanced`.
    
- **lorenz.py** → `physically_motivated_lorenz_system`, `integrate_coupled_system` (import `NumericalError` from `errors`).
    
- **operators.py** → `physical_observation_operator`.
    
- **metrics.py** → `enhanced_kling_gupta_efficiency`.
    
- **filters.py** → `EnhancedParticleFilter`.
    
- **validation.py** → `ModelValidation`.
    
- **simulation.py** → `run_enhanced_simulation` (the big orchestrator you pasted).
    

> Tip: after moving, delete the duplicate definitions from `Main.py` so only imports remain.

Each moved file should import what it needs (NumPy, SciPy, typing, etc.). Use **relative imports** inside the package, e.g.:

```python
# simulation.py (top)
import numpy as np
import matplotlib.pyplot as plt
from pathlib import Path

from .logger import logger
from .config import ModelParameters
from .errors import NumericalError
from .rainfall import generate_physically_motivated_hyetograph
from .hydrology import scs_runoff_with_uncertainty, triangular_unit_hydrograph_enhanced
from .lorenz import integrate_coupled_system
from .operators import physical_observation_operator
from .filters import EnhancedParticleFilter
from .validation import ModelValidation
from .utils import headless_setup, save_figure, safe_json_dump
```

---

## 6) Apply the three surgical fixes (without changing behavior)

### 6.1 JSON serialization error

In `simulation.py` (inside the `if save_results:` block), replace your JSON write with `safe_json_dump`:

```python
# Save arrays separately (clean)
np.savez(f"{output_dir}/simulation_arrays.npz",
         time=t,
         observations=Q_obs,
         truth=Q_true,
         ensemble_forecasts=ensemble_forecasts,
         ensemble_median=ensemble_median,
         mean=ensemble_mean,
         std=ensemble_std,
         p05=ensemble_p05,
         p95=ensemble_p95,
         states_true=states_true,
         hyetograph=hyet,
         base_runoff=q_base,
         ess_history=np.array(pf.ess_history, dtype=float))

# Save JSON summary + config safely
summary = {
    "validation_metrics": validation_metrics,
    "parameter_estimates": param_stats,
    "resampling_times": resampling_times,
    "config": {
        "CN": config.CN,
        "area_km2": config.area_km2,
        "lorenz_params": config.lorenz_params,
        "n_particles": config.n_particles,
        "lambda_ia": config.lambda_ia,
        "t_peak_hours": config.t_peak_hours,
        "t_base_hours": config.t_base_hours,
        "peak_mm_hr": config.peak_mm_hr,
        "peak_time": config.peak_time,
        "decay_rate": config.decay_rate,
        "resampling_threshold": config.resampling_threshold,
        "obs_error_base": config.obs_error_base,
        "obs_error_min": config.obs_error_min,
    },
}
safe_json_dump(summary, f"{output_dir}/summary.json")
```

(You can also keep your old `config.json` if a consumer expects it—just call `safe_json_dump(config_dict, ...)`.)

### 6.2 Replace deprecated `np.trapz`

Search/replace everywhere in the moved modules:

```bash
grep -R "np.trapz" -n stream_project monolith_backup.py
# then edit each to:
# np.trapezoid(..., dx=...)
```

### 6.3 Headless plotting (remove `plt.show()` in batch jobs)

In `simulation.py`, at the top of `run_enhanced_simulation`, call:

```python
headless_setup()
```

Then **remove** `plt.show()` calls and replace `plt.savefig(...)` with:

```python
save_figure(fig, f"{output_dir}/enhanced_simulation_results.png")
save_figure(fig_3d, f"{output_dir}/lorenz_3d.png")
```

---

## 7) Create a tiny runnable entry point

**main.py** (project root):

```python
from stream_project.simulation import run_enhanced_simulation
from stream_project.config import ModelParameters

if __name__ == "__main__":
    results = run_enhanced_simulation(ModelParameters(), save_results=True, output_dir="results")
    print("\n" + "="*60)
    print("ENHANCED HYDROLOGICAL MODELING - SUMMARY")
    print("="*60)
    vm = results["validation_metrics"]
    print(f"Final KGE Score: {vm['KGE']:.4f}")
    print(f"Nash-Sutcliffe Efficiency: {vm['NSE']:.4f}")
    print(f"CRPS: {vm['CRPS']:.4f}")
    print(f"90% Coverage: {vm['Coverage_90']:.1%}")
    print("="*60)
```

Now you’ll run the project as:

```bash
python main.py
```

---

## 8) Run and verify against baseline

```bash
python main.py | tee run_after_refactor.log
```

Compare these to the snapshot from Step 2:

- Metrics (KGE, NSE, CRPS, Coverage, Reliability) should be the same (or within tiny floating-point tolerance).
    
- PNGs should be written to `results/`.
    
- JSON should save without the `int64` crash (`summary.json` created).
    

If metrics drift noticeably, check for typos in moved imports or missing defaults.

---

## 9) Clean up the old file & commit

Once it’s working:

```bash
git add stream_project *.py results/.gitkeep 2>/dev/null || true
git commit -m "Refactor: modularize simulation, fix JSON serialization, replace trapz, headless plotting"
```

(Optionally keep `monolith_backup.py` around for a while, or remove and commit again.)

---

## 10) Optional polish (no behavior change)

- **Format/lint**: `pip install black ruff && black . && ruff check --fix .`
    
- **Type hints**: add return types to public funcs/classes.
    
- **Docstrings**: copy your excellent math comments into the modules they belong to.
    
- **Config**: allow reading a `.yaml`/`.json` to override `ModelParameters`.
    

---

## 11) (Nice-to-have) Quick smoke tests

Create `tests/test_shapes.py` to catch accidental changes:

```python
import numpy as np
from stream_project.simulation import run_enhanced_simulation
from stream_project.config import ModelParameters

def test_simulation_shapes():
    res = run_enhanced_simulation(ModelParameters(), save_results=False)
    t = res["time"]
    assert res["observations"].shape == t.shape
    assert res["truth"].shape == t.shape
    assert res["ensemble_forecasts"].shape[1] == t.size
```

Run:

```bash
pytest -q
```

---

## 12) What goes where (quick recap mapping)

- `logger` → `stream_project/logger.py`
    
- `ModelParameters` → `stream_project/config.py`
    
- `ValidationError`, `NumericalError` → `stream_project/errors.py`
    
- `generate_physically_motivated_hyetograph` → `stream_project/rainfall.py`
    
- `scs_runoff_with_uncertainty`, `triangular_unit_hydrograph_enhanced` → `stream_project/hydrology.py`
    
- `physically_motivated_lorenz_system`, `integrate_coupled_system` → `stream_project/lorenz.py`
    
- `physical_observation_operator` → `stream_project/operators.py`
    
- `enhanced_kling_gupta_efficiency` → `stream_project/metrics.py`
    
- `EnhancedParticleFilter` → `stream_project/filters.py`
    
- `ModelValidation` → `stream_project/validation.py`
    
- `run_enhanced_simulation` → `stream_project/simulation.py`
    
- Entrypoint → `main.py`
    

---

That’s it. Follow the list top-to-bottom and you’ll end up with a clean, modular codebase that:

- runs headless without warnings,
    
- saves JSON safely,
    
- avoids deprecated APIs,
    
- and is easy for your team to navigate.