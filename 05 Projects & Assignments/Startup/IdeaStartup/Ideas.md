- Pre-Flood Reminders: “FloodWatch” notifies users to charge phones, prepare kits, or move vehicles if water level is rising.
- Post-Flood Tracker: Sends update if a user’s area is cleared and safe to return.


#### Auto Last Ping Before Shutdown
- App detects that battery is critically low (e.g., 3%)
- Sends one last location and status ping to family/officials before the phone dies:
	“Jerico’s phone battery is dying. Last known location: 📍Barangay San Isidro, 4:12 PM.”

> **Prompt**
> how about sensor for detecting water level, my idea is example level 1 or the lowest, and level 2 or 3 or so on, it will compute the interval between how fast the water reach that level so we will be able to compute where does the water level will rise, another idea, is when detecting the path that is safe to go to evacuation center or find a map that will show the safest path or the path with lowest water level, so this path computation will use the water level sensor that i said
### **Concept Summary:**

App will use **smart water level sensors** that detect rising water in real-time and monitor how fast water reaches specific levels (Level 1, 2, 3, etc.). Based on the **rate of increase**, the system **predicts where and when** flooding will occur.

Simultaneously, it maps **safe routes to evacuation centers** by checking current and forecasted water levels along possible paths, showing users the **safest, driest, and fastest evacuation routes**.

The system also notifies authorities of:

- Dangerous areas
- People in need of rescue
- Fast-approaching flood zones based on predictive data

---

### 🔍 **Unique Features You Can Propose:**

---

#### **1. Flood Rise Rate Predictor**

- Uses timestamped data from water level sensors to:
    - Calculate rise rate (e.g., Level 1 ➜ Level 2 in 8 minutes)
    - Predict how fast the flood will reach critical levels
    - Give warnings in advance like:
        > “Flood expected to reach critical level in 15 minutes at Zone B.”

---

#### **2. Smart Path Finder to Evacuation Centers**

- App suggests the **safest path** using:
    - Real-time sensor data
    - Map overlays of flooded vs. dry roads
    - Elevation data
    - Flood level reports (crowdsourced or sensor-based)
    - Google Maps API
- Highlights **the safest and driest route to evacuation centers**.
- Example output:
    > “Safest route: Purok 3 ➜ San Miguel Street ➜ High Ground Road ➜ Evacuation Center B (ETA: 12 mins, low risk).”
    
---

####  **3. Flood Heatmap with Risk Forecast**

- A live map that shows:
    
    - Current flood levels
    - Predicted high-risk zones (based on rise rate)
    - Color-coded paths: 🟩 Safe, 🟨 Caution, 🟥 Danger

---

#### **4. “Panic Navigation” Button**

- One-tap feature that:
    
    - Auto-launches the safest route to the nearest shelter
    - Continuously reroutes if water levels change
    - Sends your movement to your family and authorities
        

---

#### **5. Sensor-to-Cloud Function**

- Sensors directly push data to the cloud:
    
    - Even if the user's phone dies, data is still live
    - Ensures government officials get uninterrupted updates
        

---

#### **6. Barangay-Coordinated Alerts**

- Officials receive:
    
    - Top 5 fastest rising flood areas
    - Top 3 most dangerous roads
    - List of trapped individuals (auto-generated from app usage)
        

---

#### **7. Offline Mode + Local Mesh Alert**

- If signal is lost, phones create a **local mesh network**
    - Share flood data between devices via Bluetooth or WiFi Direct
    - Alert nearby phones even without internet
    - SMS fallback for basic phones (just alerts)
	- Push notifications for battery-saving alerts
	- Offline app behavior (stores last known flood data until connected)

#### 8. Find Relief Near Me

- Shows the **nearest open relief centers**, prioritized by:
    - Distance
    - Availability of food, water, medicine
    - Capacity (how full it is)
    - Accessibility (safe route based on flood data)
        🗣️ Example:
        “Relief Center A: 300m away, low crowd, safe route ✅  
		"Relief Center B: 500m away, high crowd, road partially flooded ⚠️”

#### 9. **Request for Relief / Aid**

- Users can send a request like:
    - "Family of 5, stranded at [location], no food for 2 days"
- Authorities see request + GPS + urgency level
- Optional: add **voice message** or **photo proof**

#### 10.  **Senior Citizen Auto-Monitoring Tag**

- Add feature to register vulnerable users (like seniors or people with disabilities)
- These users can be:
    - Monitored by family accounts
    - Automatically flagged to local barangay officers in case of no response 

#### 11. **SMS-Based Backup**

- For users with **no smartphones**, allow **basic phone registration**
- Send them:
    - Text-only alerts (e.g., “Flood Level 3 at Purok 4 — evacuate now”)
    - Relief location info
- No internet required 