# System Architecture – ConnectedDrive Lite

### Overview

ConnectedDrive Lite is a web-based platform that helps BMW drivers discover, activate, upgrade, and manage digital car features. It simplifies BMW ConnectedDrive by improving visibility and accessibility, especially in regions with weak internet and limited payment options.

---

### 1. Architecture Summary

The system is built around three layers: **Frontend**, **Backend**, and **Database**.  
Each layer performs a specific role but works together through secure API communication.


---

### 2. Frontend

**Technology:** React.js (or Flutter for mobile)  
**Purpose:** Provides a simple, responsive user interface.

**Key Functions**

- Login using BMW ID, VIN, or email.  
- Dashboard showing available, new, or expiring features.  
- Feature Discovery Mode with short demos and trial activations.  
- Offline queue for upgrades when the internet is unstable.  
- Local caching using browser storage for temporary data.

---

### 3. Backend

**Technology:** Node.js with Express.js framework  
**Purpose:** Manages all core logic and connects the frontend to BMW’s servers.

**Key Functions**

- Handles authentication and user sessions.  
- Processes feature activation and renewal requests.  
- Fetches live data from BMW ConnectedDrive through REST APIs.  
- Manages offline requests and syncs when the connection restores.  
- Logs user actions for analytics and system improvement.

---

### 4. Database

**Technology:** MongoDB  
**Purpose:** Stores and manages all persistent data.

**Data Stored**

- User profiles and vehicle identifiers.  
- Available features and subscription statuses.  
- Offline upgrade queues and transaction logs.  
- Regional configurations such as currency or language.

---

### 5. Communication Flow

1. The user logs in via the frontend.  
2. The frontend sends a secure API request to the backend.  
3. The backend checks or updates data in MongoDB.  
4. The backend fetches updated information from BMW’s ConnectedDrive servers.  
5. Data is returned to the frontend for display or offline storage.

---

### 6. Technical Feasibility

- **Lightweight design:** Works efficiently in areas with poor internet.  
- **Scalability:** New car models or digital features can be added through APIs.  
- **Security:** Uses HTTPS and JWT tokens for authentication.  
- **Resilience:** Offline mode ensures usability during low connectivity.

---

### 7. Tools and Hosting

- **Frontend Hosting:** Vercel or Netlify  
- **Backend Hosting:** Render or AWS  
- **Database Hosting:** MongoDB Atlas  
- **Version Control:** GitHub  
- **Design & Prototyping:** Visily, Lovable
