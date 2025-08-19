---
tags:
  - literature
source: 
created: 2025-06-23
Type: "[Lecture | Book | PDF | Video]"
---

### 📖 Summary:

## 📦 ES6 Modules – Summary

### 🔑 What Are ES6 Modules?

- ES6 Modules (ESM) allow JavaScript code to be **split across multiple files** with **clear boundaries**.
- Each file (module) has its **own private scope**.
- We use `export` to expose values, and `import` to bring them into other files.
- Helps avoid **global scope pollution** and keeps code organized.

---

### 🌍 Before ES6 Modules

- Multiple `<script>` tags loaded in HTML shared the **global scope**.
- Variables from one file could leak into another unintentionally.
- Solution: IIFEs (Immediately Invoked Function Expressions) were used to create isolated scopes.

---

### 📤 Exporting

#### ✅ Named Export



```javascript
// math.js 
export const add = (a, b) => a + b; 
export { subtract };
```

- Allows multiple exports.
    
- Must import using **exact names**.
    


```js
import { add, subtract } from './math.js';
```

#### ✅ Default Export


```js
// greet.js 
export default "Hello";
```

- One default export per file.
- Can be imported with **any name**.


```js
import greeting from './greet.js';
```

#### ✅ Mixed Export

```js
export default login; 
export const logout = () => {}; 
import login, { logout } from "./auth.js";
```

---

### 📥 Importing

- Named: `import { x } from "./file.js";`
- Default: `import x from "./file.js";`
- Mixed: `import x, { y } from "./file.js";`
    

---

### 📌 Rules & Behavior

- File must be loaded with `<script type="module">`.
- Modules are **deferred automatically** — no need for `defer`.
- Import paths must be **string literals**.
- Variables/functions not exported **can’t be accessed** elsewhere.
- **Only one default export per file**.

---

### 🔁 Re-exporting

js

CopyEdit

```js
export * from './math.js'; 
export { add } from './math.js';
```

Used to aggregate exports in an index file.

---

### ⚠️ Errors & Pitfalls

- Importing a non-existent named export = ❌ error.
- Confusing naming with default vs named can lead to bugs.
- Can't use modules with `file://` — must use a **local dev server**.
    

---

### 🧠 When to Use What

- Use **named exports** for utility libraries (many functions)
- Use **default export** when the module has a **single main purpose**.
- Be consistent in teams — mixing can be confusing.

---

### 🧪 Dev Tip

Use a dev server like:

- **Live Server (VS Code extension)**
- `python -m http.server`
- `npm run dev`

### 💡 Key Ideas:
- 

### 🗣 In my own words:
- 

### ➡ Related permanent notes:
- 
