<!-- SHOWCASE: false -->

# University Event Management System

> A full-stack web application for discovering, creating, and managing university campus events, scoped by institution, RSO membership, and

![Status](https://img.shields.io/badge/status-complete-brightgreen)
![Language](https://img.shields.io/badge/language-JavaScript%20%7C%20HTML%20%7C%20CSS%20%7C%20SQL-blue)
![Semester](https://img.shields.io/badge/semester-Spring%202024-orange)

---

## Course Information

| Field                  | Details                                                                                                                                                                                                                                                        |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Course Title           | Database Systems                                                                                                                                                                                                                                               |
| Course Number          | COP4710                                                                                                                                                                                                                                                        |
| Semester               | Spring 2024                                                                                                                                                                                                                                                    |
| Assignment Title       | Full Stack Development Final Project                                                                                                                                                                                                                           |
| Assignment Description | Design and implement a full-stack web application backed by a relational database. The project required a complete MySQL schema, a RESTful API layer, and a React frontend, demonstrating end-to-end integration across all tiers of a modern web application. |

---

## Project Description

A React single-page application paired with a Node.js/Express backend and MySQL database, built for managing campus events across multiple Florida universities. Users register under one of three roles: standard user, RSO member, or university administrator, each unlocking different event creation and review capabilities. An interactive OpenLayers map centers on the user's affiliated university and renders event location pins fetched from the backend API.

---

## Screenshots / Demo

> _No screenshot available. Add one with: `![Demo](docs/your-image.png)`_

---

## Results

When running correctly, the application serves a login page at `http://localhost:3000`. After authenticating, the main page loads with a university-centered OpenLayers map and an event feed. Expected console output during startup:

```bash
# Terminal 1 - React dev server
Compiled successfully!
Local: http://localhost:3000

# Terminal 2 - Express/Node server
Server running on port 3001

# Browser console (on main page load)
University:  UCF
Coords:  { lat: 28.6024, long: -81.2001 }
Map center coords... Long -81.2001 || Lat: 28.6024
Generating map
```

Key things to verify: the map renders centered on your university, event pins appear when events are present, and role-specific navigation items are visible. If the map does not render, confirm your OpenLayers dependency is installed and the `#map` div is receiving a non-zero height from the stylesheet. If events do not load, check that `server.js` is running on port 3001 and that your MySQL credentials are correct.

---

## Key Concepts

`role-based access control` `React SPA routing` `OpenLayers map integration` `RESTful API (Axios)` `MySQL relational schema` `session management (cookies)` `multi-tenant university scoping` `RSO lifecycle management`

---

## Languages & Tools

- **Languages:** JavaScript (React), HTML, CSS, SQL, Batch
- **Framework/SDK:** React 18, React Router v6, Node.js, Express
- **Database:** MySQL
- **Mapping:** OpenLayers (`ol`)
- **HTTP Client:** Axios
- **Cookie Management:** js-cookie
- **Build System:** Create React App (npm)

---

## File Structure

```
project-root/
├── server.js                         # Express API server; handles all backend routes
├── sql/
│   └── init_db_main.sql              # Database initialization script
├── src/
│   ├── App.js                        # Root component; defines all client-side routes
│   ├── index.js                      # React DOM entry point
│   ├── index.css                     # Global styles
│   ├── reportWebVitals.js            # CRA performance reporting utility
│   ├── images/                       # Static assets (map pin, fullscreen icons)
│   ├── css/
│   │   └── MainPageStyles.css        # Styles for the main map/feed layout
│   ├── pages/                        # Thin page wrappers; one per route
│   │   ├── LoginPage.js
│   │   ├── RegisterHandlerPage.js    # Routes user to correct registration flow
│   │   ├── NewUserRegisterPage.js
│   │   ├── NewRSOUserRegisterPage.js
│   │   ├── ExistingRSOUserRegisterPage.js
│   │   ├── UniversityUserRegisterPage.js
│   │   ├── MainPage.js               # Map + event feed; core application view
│   │   ├── FeedbackPage.js
│   │   ├── CreateRSOEventPage.js
│   │   ├── CreateUniEventPage.js
│   │   ├── EditEventPage.js
│   │   └── ReviewEventPage.js
│   └── components/                   # Feature-grouped UI components
│       ├── LoginRegisterComp/        # Login and registration form variants
│       ├── MainPageComp/             # Header and event feed section
│       ├── EventPageComp/            # RSO/university event creation forms; uses Google Geocoding API
│       ├── FeedbackPageComp/         # Event feedback and comments feed
│       └── ReviewEventPageComp/      # Event review header and feed (admin role)
└── package.json
```

---

## Installation & Usage

### Prerequisites

- Node.js >= 18
- npm >= 9
- MySQL >= 8
- A valid Google Geocoding API key

### Setup

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/UCF-COP4710-UniversityEventMgmt.git
cd UCF-COP4710-UniversityEventMgmt

# 2. Install dependencies
npm install

# 3. Add your Google Geocoding API key
#    Open src/components/EventPageComp/ and replace [API KEY HERE] with your key

# 4. Initialize the database
cd sql
mysql --host=localhost --user=root --password=admin
# Inside the MySQL shell:
source ./init_db_main.sql
exit

# 5. Configure server credentials (if not using root/admin defaults)
#    Edit server.js and update the MySQL username and password fields

# 6. Start the backend server (Terminal 1)
cd ..
node server.js

# 7. Start the React dev server (Terminal 2)
npm start
# App available at http://localhost:3000
```

---

## Contributors

| Name            | Role                                                                                                    | GitHub                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| Alexander Green | Frontend development, API revision and implementation, map creation and integration, Project Management | [@alexneilgreen](https://github.com/alexneilgreen)     |
| Rylan Simpson   | Database design, API creation, Recurrsive Feature Testing, Project Management                           | [@CATastrophic141](https://github.com/CATastrophic141) |

---

## Academic Integrity

This repository is publicly available for **portfolio and reference purposes only**.
Please do not submit any part of this work as your own for academic coursework.
