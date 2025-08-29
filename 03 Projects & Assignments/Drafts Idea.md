**Title:** 
**Target Users: Citizens, Authorities,** 

- **Web App ~~(for LGU/authorities)~~  Higher-Ups/Authorities:** 
    - Control panel to:
        - **Trigger alerts/alarm**.
        - ~~Choose barangay-specific announcements.~~
	        - ~~Monitor risk levels (based on data). **Note: if there is a data we can use**~~
    - Logs all alerts for record-keeping and future analysis. or (View alert history/logs)
    - Admin login
    - View sensor data (rainfall from rain gauge, and the 2 other existing IOT of Naga City)
    - Maybe it trigger alerts based on readings

- **Mobile App (for citizens):**
    - Turns the phone into a ~~backup megaphone~~ make it like an alarm or just notification or alarm(plays warning sounds).
    - Push notifications for alerts.
    - Can work offline.
    - Lightweight, simple interface - no login needed.
- Maybe we can add feature like:
	- Users select their **barangay** when installing the app.
	- If flooding is reported or detected in nearby barangays, they receive early warning notifications.
### Gap
- No historical data of local floods just historical data of previous typhoon
- Need to create an app to determine the historical data of floods
- Need to enable to notify on phones of the residents even on silent, no internet, or even low battery **(I thinks this solution is not hitting a pain point)**
	- People often aren’t prepared until it’s too late (e.g., no time to charge phones, evacuate early). 
- How about the first baranggay
- There is a protocol that need the barangay official to consult to higher up before they announce something like "evacuate now"


### Possible Solution
- Mobile app that will serve as warning to prepare especially on the vulnerable barangays in naga city. **(But How can we know the vulnerable Barangay)**
	- If a near barangay is currently flooding, the app will still notify to other nearest barangay to prepare early if needed to  evacuate to charge their devices, and to be ready. For example **"If Barangay Panicuason(A) floods, alert Barangays B, C, D (nearest barangay) based on closeness and terrain."**
	- If flooding is reported or detected in nearby barangays, they receive **early warning notifications**.
	- Notification will include:
		- What near area is currently affected
		- Current water level status (ex., normal, alert, critical) (**If there is data**)
		- Recommended actions(ex.,  prepare to evacuate, move to higher ground, charge devices **(For the possibility of power interruption)**)
	- Or just for example "Barangay Sta. Cruz reported flood (level 3). You are within 2km. Please prepare to evacuate or charge devices." (Maybe we can get the flood level based on data of DRRM, if there is)
	-  **Example Alert Message**: ***“Flood detected in Barangay Sta. Cruz (Level 3). You are within 2km. Prepare to evacuate or charge devices in case of power outage.”***
- Integrate the LORAWAN Tech (Base it on the skill of my team if We can do it)

- **How about Community reports** - Maybe mobile app?
	- Users can **manually report flooding** in their area
- How about assigning **Flood Risk Score** per Barangay based on **Elevation, Rain Intensity, Past reports.** **(We can get the data via profiling I Guess)**
	- The maybe visually show these in the app with color-coded risk zones

