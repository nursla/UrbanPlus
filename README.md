# UrbanPlus
Ankara sakinleri için geliştirilmiş; harita tabanlı, gerçek zamanlı kentsel sorun bildirme ve yönetim platformu. (React + Firebase + Leaflet)

# 🏙️ Urban+ | Ankara Urban Improvement Platform

![License](https://img.shields.io/badge/License-MIT-blue.svg) ![React](https://img.shields.io/badge/React-18.0-61DAFB?logo=react) ![Firebase](https://img.shields.io/badge/Firebase-Supported-FFCA28?logo=firebase) ![Status](https://img.shields.io/badge/Status-Active-success)

[![Live Demo](https://img.shields.io/badge/Canlı_Demo-Uygulamaya_Git-orange?style=for-the-badge&logo=firebase&logoColor=white)](https://urbanplus.web.app)

<div align="center">
  <img width="1490" height="847" alt="image" src="https://github.com/user-attachments/assets/24907caf-678c-41cb-ba64-4d986cffc9d1" />

  <br/>
  <h3>Track, Report, Resolve. Shaping Ankara Together.</h3>
</div>

---

## 📖 Project Overview

**Urban+** is a modern **Urban Tracking System** designed for the residents of Ankara. It allows citizens to report local urban issues (potholes, lighting failures, environmental pollution, etc.) using a map-based interface, while enabling municipality teams to track and manage these reports via a secure administrative dashboard.

The primary objective is to bridge the gap between citizens and the **Ankara Metropolitan Municipality**, fostering a participatory approach to city management using modern web technologies and geospatial visualization.

## [🌍 View Live Demo]([https://github.com/GMT-458-Web-GIS/full-stack-web-gis-nursla](https://urbanplus.web.app))
https://urbanplus.web.app

---

## ✨ Key Features

* **Interactive Map Interface:** Seamless navigation across Ankara using Leaflet.js.
* **Location-Based Reporting:** "Drop a pin" functionality to report issues with exact coordinates.
* **Real-Time Evidence:** Upload photos of urban issues directly to Firebase Storage.
* **Smart Categorization:** Filter reports by type or status.
* **Administrative Dashboard:** A dedicated panel for municipality teams to manage issue lifecycles.
* **GeoJSON Integration:** Visualization of Ankara's official district boundaries.
* **Role-Based Security:** Distinct interfaces for Guests, Citizens, and Admins.
---
## 🎨 Corporate Identity & Colors

The project is designed in alignment with the Ankara Metropolitan Municipality's official corporate identity:
- 🟦 **ABB Navy:** `#093e88` (Primary Theme)
- 🧊 **ABB Blue:** `#00abe5` (Buttons & Accents)
- ⬜ **Off-White:** `#fffeff` (Typography & Backgrounds)
---

## 🛠️ Technologies Used

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | React 18 (Vite) | High-performance user interface & component management |
| **Mapping** | React Leaflet | Map rendering, markers, and spatial interaction |
| **Backend (BaaS)** | Firebase | Authentication, Hosting, and Serverless functions |
| **Database** | Firestore (NoSQL) | Real-time data syncing for reports and user profiles |
| **Storage** | Firebase Storage | Hosting user-uploaded images (evidence photos) |
| **Routing** | React Router v6 | Protected routes and navigation guards |
| **Styling** | CSS Modules / Styled | Responsive design aligned with ABB corporate identity |

---

## 🏗️ System Architecture

Urban+ follows a **Serverless Architecture** where the frontend handles all client-side logic and spatial rendering, while Firebase acts as the backend-as-a-service (BaaS) provider.

* **Authentication Layer:** Firebase Auth handles Identity Management (IDM) and role verification (Guest vs. Admin).
* **Data Layer:** Firestore stores report metadata, geolocation points, and status updates in real-time.
* **Media Layer:** Images uploaded by citizens are optimized and stored in Firebase Storage buckets.
* **Presentation Layer:** React components render the map and dashboard, communicating with Firebase via the Web SDK.

---
## 👤  User Roles & Access Control

### 1. Guest (Visitor)
* **View Access:** Can view the interactive map and browse existing urban reports.
* **Filtering:** Can filter reports by category (e.g., Road) to see issues in specific neighborhoods.
* **Restriction:** Cannot report new issues, upload photos, or access the admin panel.

### 2. Citizen (Authenticated User)
* **Report Issues:** Can use the "Drop Pin" feature to submit new urban issues with precise location data.
* **Upload Evidence:** Can attach real-time photos to their reports using Firebase Storage integration.
* **Track Status:** Can monitor their submitted reports to see if they are marked as "In Progress" or "Resolved".
* **Manage Own Data:** Can delete their own reports if they were submitted in error (before admin intervention).

### 3. Admin (Municipality Staff)
* **Full Control:** Secure access to the Admin Dashboard with advanced management tools.
* **Status Management:** Authority to update the lifecycle of a report (Open → In Progress → Resolved).
* **Internal Feedback:** Can add "Admin Notes" to specific reports for internal team communication and task delegation.
* **Moderation:** Can delete inappropriate, duplicate, or resolved reports from any user to maintain data quality.

---

## 📊 CRUD Operations Matrix

| Operation | Guest | Citizen | Admin |
| :--- | :---: | :---: | :---: |
| **View Map & Reports** | ✅ | ✅ | ✅ |
| **Filter & Search** | ✅ | ✅ | ✅ |
| **Create Report** | ❌ | ✅ | ✅ |
| **Upload Photo** | ❌ | ✅ | ✅ |
| **Update Status** | ❌ | ❌ | ✅ |
| **Add Admin Notes** | ❌ | ❌ | ✅ |
| **Delete Own Report** | ❌ | ✅ | ✅ |
| **Delete Any Report** | ❌ | ❌ | ✅ |

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites
* **Node.js** (v16 or higher)
* **npm** or **yarn**
* A Google **Firebase** Project (Free Tier is sufficient)

### Installation

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/GMT-458-Web-GIS/full-stack-web-gis-nursla.git](https://github.com/GMT-458-Web-GIS/full-stack-web-gis-nursla.git)
    cd full-stack-web-gis-nursla
    ```

2.  **Install Dependencies**
    ```bash
    npm install
    ```

3.  **Configure Environment Variables**
    Create a `.env` file in the root directory and add your Firebase credentials.
    *(You can find these in your Firebase Console > Project Settings)*

    ```env
    VITE_API_KEY=your_api_key_here
    VITE_AUTH_DOMAIN=your_project.firebaseapp.com
    VITE_PROJECT_ID=your_project_id
    VITE_STORAGE_BUCKET=your_project.appspot.com
    VITE_MESSAGING_SENDER_ID=your_sender_id
    VITE_APP_ID=your_app_id
    ```

4.  **Run the Application**
    Start the local development server:
    ```bash
    npm run dev
    ```
    Open your browser and navigate to `http://localhost:5173`.

---

## 🔮 Future Improvements

Constantly working to improve Urban+. Here is roadmap:

- [ ] **Mobile Application:** Developing a React Native version for iOS and Android for on-the-go reporting.
- [ ] **Notification System:** Email or SMS alerts when a report status changes.

---

## 📄 License

This project is developed for educational purposes within the scope of the Web GIS course and is available under the [MIT License](LICENSE).

<br/>

<div align="center">
  <p>Built with ❤️ for <b>Ankara</b></p>
  <p><sub>Developed by Nur Sıla Özkan </sub></p>
</div>

---
