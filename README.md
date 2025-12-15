# OptiSigns – SCIO Clone MVP Plan

## 1. MVP Overview

The MVP is a **screen-first digital signage web application**, designed to replicate the core functionality of SCIO.

The main goal of this MVP is to validate the most important business flow of OptiSigns:

> **Managing screens and displaying assets on screens**

In this MVP:

- **Screen is the core feature**
- Each **Screen is associated with exactly one Asset** (image or video)
- Assets are played via a **web-based mock player**, acting as a real device

Advanced concepts such as playlists, scheduling, advanced real-time sync, native TV apps, billing, etc. are **intentionally excluded** to keep the scope suitable for ~3 focused working days.

---

## 2. High-level TODOs

### Planning & Design

- Review the SCIO walkthrough and explore app.optisigns.com
- Define MVP scope with a screen-first approach
- Design core entities and data relationships

### Backend

- Initialize the project
- Design database schema
- Implement authentication (JWT)
- Build APIs for Screen, Asset, and Player
- Implement Player ↔ Screen pairing logic

### Frontend

- Authentication flow
- Screen management UI
- Asset management UI
- Assign Asset to Screen
- Web Player page (device simulation)

### Finalization

- Seed sample data
- Input validation and basic error handling
- Prepare content for interview presentation

---

## 3. MVP Features

### Authentication

- Email/password login
- JWT-based authentication
- Protect the entire admin web app (Dashboard, Screen, Asset)
- Only authenticated users can:

  - Create / edit / delete Screens
  - Upload and assign Assets

### Player (Device Simulation)

- Web player accessible at `/player`
- Player self-registers with the backend and receives a unique **playerId**
- Player displays its playerId for the user to use when creating a Screen
- Each user has one player for testing

### Screen Management (Core Feature)

- Create / edit / delete Screens
- When creating a Screen, the user selects a **playerId** to pair
- Each Screen is assigned **exactly one Asset**
- Ability to change the Asset of a Screen
- Screen properties:

  - Name
  - playerId
  - Assigned Asset (nullable)

### Asset Management

- Add Asset (upload image/video)
- Preview and delete Asset

### Mock Player Playback

- Player calls backend APIs to fetch Screen and Asset by playerId
- Once paired, the player starts playing the assigned Asset
- Fullscreen playback of the Asset on the web player

---

## 4. Detailed Planning & Timeline (3 days – 8h/day)

### Day 1 – Foundation & Screen Core (8h)

- **Product understanding (0.75h):** Review SCIO and confirm screen-first flow and player–screen pairing
- **Architecture & data design (0.75h):** Entities: User, Player, Screen, Asset
- **Project setup (0.75h):** Backend and frontend skeleton
- **Authentication (1h):** Register, login, JWT
- **Screen & Player APIs (2h):** Screen CRUD, Player registration, pairing logic
- **Screen UI (2.75h):** Create, edit, delete, list Screens and input playerId

### Day 2 – Asset Management (8h)

- **Buffer & review (1.5h):** Seed data, validation, UI polish, re-test Day 1
- **Asset upload & delete APIs (3h):** Upload image/video, file storage, DB records, deletion
- **Asset management UI (3h):** Create, list, preview, delete Assets
- **Assign Asset to Screen (0.5h):** Select Asset for each Screen

### Day 3 – Mock Player & Finalization (8h)

- **Fixes & optimization (1h):** UI/API bug fixes and test runs
- **Mock Player APIs (2h):** APIs for Player to fetch Screen & Asset by playerId
- **Player UI (2h):** Fullscreen web player rendering Assets
- **Testing (1.5h):** End-to-end testing, bug fixing, comparison with real app behavior
- **Demo & interview prep (1.5h):** Prepare slides and demo notes

---

## 5. Notes

This MVP focuses on validating the core value of a digital signage system: **pairing a device (player) with a screen and controlling displayed content**. The architecture is intentionally minimal but can be extended in the future with playlists, scheduling, real-time communication, and native TV players.
