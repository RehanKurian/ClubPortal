# ClubPortal

Lightweight club management portal (frontend + backend) for managing clubs, events, announcements and members.

This repository contains a Vite + React frontend and an Express + Mongoose backend. The README below documents only the tools, files and commands that are actually present and used in this repository.

---

## Table of contents

- [Project structure](#project-structure)
- [Tech stack / Dependencies](#tech-stack--dependencies)
- [Prerequisites](#prerequisites)
- [Local setup — backend](#local-setup---backend)
- [Local setup — frontend](#local-setup---frontend)
- [Important files / where to look](#important-files--where-to-look)
- [Database models](#database-models)
- [Notes](#notes)

---

## Project structure

Top-level layout (relevant files and directories present in this repo):

- backend/  
  - app.js — main Express server file (server entry point)  
  - package.json — backend dependencies (express, cors, mongoose)  
  - package-lock.json  
  - models/ — Mongoose model definitions
    - Announcementinfo.js
    - Clubinfo.js
    - Clubmembers.js
    - Eventinfo.js
    - Eventmembers.js
    - User.js
  - uploads/ — directory present for uploaded files

- frontend/  
  - package.json — frontend dependencies and scripts (Vite + React + MUI + axios + react-router-dom + react-hook-form)  
  - package-lock.json  
  - index.html  
  - vite.config.js  
  - eslint.config.js  
  - public/
    - MCKA.svg
    - team.svg
  - src/
    - main.jsx — app bootstrap
    - App.jsx — application router / top-level component
    - index.css, App.css
    - components/ — React components and corresponding CSS files (examples)
      - Header.jsx, Footer.jsx, Clubs.jsx, Events.jsx, Announcements.jsx, Profile.jsx, Login.jsx, Sidebar.jsx, ProtectedRoutes.jsx, Memberdashboard.jsx, Admindashboard.jsx, SuperAdmin.jsx, AdminEvents.jsx, AdminMembers.jsx, AdminAnno.jsx, AdminReports.jsx, Admin style/CSS files, etc.
    - assets/ — (folder present)

- package.json (root) and package-lock.json (root) — small root files present

---

## Tech stack / Dependencies

Backend (see `backend/package.json`):
- Node.js + Express
- Mongoose (MongoDB ODM)
- cors

Frontend (see `frontend/package.json`):
- Vite
- React (React 19)
- React DOM
- @mui/material, @mui/icons-material
- axios
- react-hook-form
- react-router-dom
- Dev: @vitejs/plugin-react, eslint and related packages

---

## Prerequisites

- Node.js (recommended current LTS)
- npm (bundled with Node.js)
- MongoDB (a running MongoDB instance for the backend)

---

## Local setup — backend

1. Install dependencies:
   - cd backend
   - npm install

2. Configure database and other environment settings:
   - The server entry point is `backend/app.js`. It contains the code that connects to MongoDB and starts the HTTP server. Edit `backend/app.js` to point to your MongoDB connection string (or supply the environment variables that `app.js` reads if it uses them).
   - Ensure the uploads directory (`backend/uploads/`) is writable if you use file upload routes.

3. Start the server:
   - From the repository root:
     - node backend/app.js
   - (There is no `start` script defined in `backend/package.json`, so starting with `node` is the straightforward way.)

Start the backend before running the frontend so the client can connect to the API.

---

## Local setup — frontend

1. Install dependencies:
   - cd frontend
   - npm install

2. Development server (Vite):
   - npm run dev
   - Vite's dev server will serve the frontend (default port 5173 unless configured otherwise).

3. Build for production:
   - npm run build
   - Preview the production build:
     - npm run preview

---

## Important files / where to look

- backend/app.js — backend server, routes and DB connection logic.
- backend/models/*.js — Mongoose schemas for the main entities.
- frontend/src/main.jsx — React application bootstrap.
- frontend/src/App.jsx — top-level routing and layout.
- frontend/src/components/ — primary UI components (Header, Footer, Clubs, Events, Announcements, Login, Profile, dashboards and admin components).
- frontend/vite.config.js — Vite configuration.
- frontend/eslint.config.js — ESLint configuration used by the frontend.

---

## Database models

The repository contains the following Mongoose model files (see `backend/models/`):

- Announcementinfo.js — announcement records
- Clubinfo.js — club metadata
- Clubmembers.js — club membership entries
- Eventinfo.js — event metadata
- Eventmembers.js — event participation entries
- User.js — user accounts

## Notes

- This repository is a combined frontend + backend project. Start the backend first, then the frontend dev server.
- There is no explicit license file or LICENSE entry in the repository metadata.
- Issues are disabled for this forked repository (see repository settings); please open a PR or reach out directly to the repository owner for contribution coordination.
