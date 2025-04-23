Project Overview:
**Title:** Faculty Work Hours Tracker  
**Team:** Cyber Rookies  
**Target Users:** Faculty members and administrative staff of Graphic Era Hill University (Bhimtal Campus)

**Objective:**  
To digitally track, manage, and monitor the work hours of faculty members through a simple login/punch-in/punch-out system with location validation via geofencing.

---

### 🧵 Key Features:
- **Role-based Login** for faculty and admin
- **Punch In / Punch Out** system with live location tracking
- **Geofencing logic** using latitude, longitude, and radius comparison
- **Data stored in localStorage** (for demo); can be expanded to Firebase or MongoDB
- **Admin Panel** to manage users, view reports, and monitor targets
- **Weekly Hours Compliance Charts** via Chart.js
- **Responsive UI** built with TailwindCSS
- **User Feedback & Alerts** using SweetAlert2

---

### 📈 Technology Stack:
- **Frontend:** HTML, Vue.js, TailwindCSS
- **Charts:** Chart.js
- **Notifications:** SweetAlert2
- **Icons:** Bootstrap Icons
- **Storage (demo):** localStorage

---

### 📊 Geofencing Logic:
We implemented a location-based boundary check using the **Haversine Formula**. It compares the device's current GPS location (via `navigator.geolocation`) to the university's central coordinates (set to Bhimtal Campus) with a radius of 500 meters.

- **Campus Lat/Lng:** 28.910450, 77.710869
- **Allowed Radius:** 500 meters

**Why Geofencing?**
- Prevents remote location misuse (like punching in from home)
- Ensures that punch in/out happens **only on campus**
- Used in real-world apps like Zomato, Uber for location validation

**Why 500 meters?**
- Small campuses can face GPS inaccuracies
- 500m radius is practical to tolerate **device GPS errors** while still maintaining security

**User Location Source:**
- Pulled from browser's built-in GPS via `navigator.geolocation.getCurrentPosition()`
- Permission must be granted manually by the user

---

### 🛡️ Punch In / Punch Out Code Highlights:
- Validates campus location before marking entry/exit
- Calculates total work hours based on timestamps
- Handles location denial via graceful alerts
- Persists data in localStorage for history logging

---

### 🌐 UI Snapshots (Delivered Files):
- `FACULTYay.html` — Main frontend interface
- `hi.jpg` — Banner image for Bhimtal campus branding

---

### ✈️ Future Scope (Phase 2):
- Add **Firebase backend** for real-time login & data sync
- Include **OTP/face verification** for anti-spoofing
- Auto punch-out after inactivity
- Real-time GPS updates & map view for admin
- Convert to **PWA** for mobile app experience

---
