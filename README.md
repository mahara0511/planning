# SCIO (OptiSigns Clone) - Enterprise Digital Signage Platform

A project to build a comprehensive Digital Signage management platform, comprising a Cloud-based administration system (CMS) and a content playback application for devices (Player App).
The detailed plan of this project can be seen here: https://docs.google.com/spreadsheets/d/1tye-7tq9IO2VjYyD5eorjX9VhyEq_bGWEwC346MRGFc/edit?gid=0#gid=0

## Tech Stack

- **Backend:** Node.js (NestJS), MongoDB (Database), Redis (Caching).
- **Frontend:** Angular (Admin Dashboard), Stripe Elements (Billing).
- **Infrastructure:** AWS EC2 (Server), AWS S3 (Storage), AWS CloudFront (CDN).
- **Player App:** Android (Kotlin) / WebOS / Tizen / Web App.

---

## PART 1: SCIO CLOUD CMS (Web Dashboard)

The central system for managing content, devices, and users.

### 1. Content & Design Studio

- [ ] **Asset Management:**
  - Multi-format upload: Images, Videos, Documents.
  - Folder management, Grid view, Search.
- [ ] **Online Design Studio:**
  - **Templates Library:** Pre-designed templates by theme (Holidays, Menu...).
  - **AI Designer:** Enter prompts for AI to generate template layouts.
  - **Canvas Editor:** Drag-and-drop tool for text, images, and shapes to create designs from scratch (Canva-like).
- [ ] **Playlist Builder:**
  - Create Playlists, add Assets/Templates.
  - Order arrangement (Drag & Drop), adjust Duration and Transition effects.

### 2. Device Management

- [ ] **Screen Pairing:** Connect new devices via a 6-digit "Pairing Code".
- [ ] **Live Dashboard:** Monitor Online/Offline status and currently playing content.
- [ ] **Content Assignment:** Assign Playlists, Schedules, or Loops to individual screens/groups.

### 3. Operations & Automation

- [ ] **Smart Scheduling:** Schedule content playback by specific date/time (Calendar View).
- [ ] **Operational Schedule:** Set automatic Screen Power On/Off schedules to save energy.
- [ ] **Monitoring Alerts:** Configure Email alerts when devices lose connection for a specified duration.
- [ ] **System Preferences:** Global system defaults (Password Policy, Default Duration, Image Scaling).

### 4. Engage Hub (Interaction Config)

- [ ] **Touch Kiosks:** Enable/Disable touch mode, set destination URL for Kiosks.
- [ ] **QR Generator:**
  - **QR Overlay:** Create static QR Codes (Wifi, Web) overlaying content.
  - **Scan-to-Interact:** Create dynamic QR Codes for mobile screen control.
  - **Check-in/Review:** QR codes leading to check-in forms or reviews.
- [ ] **IoT Triggers:** Configure "Lift & Learn" rules (Lift product -> Change content).

### 5. Commercial & Store

- [ ] **Billing Portal:**
  - Select Subscription Plan (Free/Pro), add payment cards (Stripe Integration).
  - Invoice History & Sub-Account Billing management (Agency).
- [ ] **Hardware Store:**
  - Player ordering page, quantity selection, shopping cart.
  - Track order status (Order History).

### 6. Enterprise & Advanced

- [ ] **Team Management:** Invite members, role-based access control (RBAC).
- [ ] **Security & Logs:** Audit Log (Activity history), SSO (SAML Login).
- [ ] **Branding:** Customize Logo, Favicon, Custom Subdomain.
- [ ] **Analytics:** Proof-of-Play reports (play count), CSV export.
- [ ] **Collaboration:** Share Links (Public Playlist sharing with password protection).
- [ ] **Integrations:** Google Calendar, Tableau, API Keys, RS232 Commands.

### 7. Support

- [ ] **Help Center:** Documentation (Docs), Video Tutorials, Submit Support Tickets.

---

## PART 2: SCIO PLAYER APP (TV Software)

Application running on endpoint devices.

### 1. Core Engine

- [ ] **Pairing:** Display 6-digit connection code.
- [ ] **Sync & Cache:** Realtime content sync from Cloud, cache storage for Offline playback.
- [ ] **Rendering:** Smooth rendering for Video (4K), Images, HTML5.

### 2. Engage Runtime

- [ ] **Touch Handler:** Handle touch events for Kiosk mode.
- [ ] **Mobile Controller:** Connect WebSocket with user mobile phones (via Scan-to-Interact QR).
- [ ] **IoT Listener:** Listen for peripheral sensor signals (Lift & Learn).
- [ ] **AI Processing:** Detect viewers via Camera (if available).

### 3. System Control

- [ ] **Power Management:** Execute Screen On/Off commands from Operational Schedule.
- [ ] **Heartbeat & Logs:** Send Online signal and content playback logs to Server.

## IMPLEMENTATION ROADMAP

This roadmap is structured to prioritize core functionality, followed by operational control, user support, monetization, and finally advanced enterprise features.

### PHASE 1: THE FOUNDATION (Core Loop)

_Goal: Establish the basic loop (Upload -> Playlist -> Play on TV)._

**Backend & Frontend CMS:**

- [ ] **Auth:** User Registration, Login, Forgot Password (JWT).
- [ ] **Asset Management:** Multi-format upload (Images/Videos/Docs) to S3, Folder management.
- [ ] **Playlist Builder:** Create playlists, drag-and-drop ordering, duration settings.
- [ ] **Screen Pairing:** Generate 6-digit "Pairing Code" and manage device connections.

**Player App:**

- [ ] **Core Engine:** Pairing screen UI, Real-time Content Sync (Socket/Polling), Offline Caching & Playback.

---

### PHASE 2: OPERATIONS & CONTROL

_Goal: Remote device control and automated scheduling._

**Backend & Frontend CMS:**

- [ ] **Smart Scheduling:** Calendar view for scheduling content by specific date/time slots.
- [ ] **Ops Schedule:** Configure automatic Screen Power On/Off schedules to save energy.
- [ ] **Monitoring Alerts:** System rules to send Email alerts when devices go offline.
- [ ] **Live Dashboard:** Visual indicator of Online/Offline status for all screens.

**Player App:**

- [ ] **Power Manager:** Execute Power On/Off commands based on Ops Schedule (HDMI-CEC or Black Screen).
- [ ] **Heartbeat:** Send "I'm alive" signals to the server every 30s.

---

### PHASE 3: SUPPORT & USER SUCCESS

_Goal: Ensure users understand the system before upgrading._

**Frontend CMS:**

- [ ] **Help Center UI:** A dedicated Knowledge Base portal.
- [ ] **Ticketing System:** Form to submit support requests (integrated with email or helpdesk tools).
- [ ] **Video Tutorials:** Hub for instructional videos.

**Content Creation:**

- [ ] **Docs:** Write guides for Phase 1 & 2 features (Pairing, Playlists, Scheduling).

---

### PHASE 4: MONETIZATION (Commercial)

_Goal: Enable revenue streams via Subscriptions and Hardware sales._

**Backend & Frontend CMS:**

- [ ] **Billing Integration:** Integration with Stripe for Subscription plans (Free/Pro/Enterprise).
- [ ] **Hardware Store:** E-commerce section to order Player devices (Stick/Box), Shopping Cart, Checkout.
- [ ] **Invoices & Orders:** Invoice history for subscriptions and Order tracking for hardware.
- [ ] **Sub-Accounts:** Billing management for Agencies/Resellers.
- [ ] **Profile:** Comprehensive User and Company profile settings.

---

### PHASE 5: DIFFERENTIATION (Design & Engage)

_Goal: "Killer Features" for interactive experiences and content creation._

**Backend & Frontend CMS:**

- [ ] **Online Design Studio:**
  - **Templates:** Pre-made designs & AI Designer prompts.
  - **Canvas Editor:** Canva-like drag-and-drop tool (Text, Images, Shapes).
- [ ] **Engage Hub:** Configuration for Kiosk URLs, QR Overlays, and IoT Rules.

**Player App (Engage Runtime):**

- [ ] **Touch Mode:** Handle touch events to switch to Kiosk Webview.
- [ ] **Mobile Control:** WebSocket connection for "Scan-to-Interact" (Control screen via phone).
- [ ] **IoT Listener:** Trigger content changes based on peripheral sensors (Lift & Learn).

---

### PHASE 6: ENTERPRISE & SCALE

_Goal: Features for large-scale organizations and security._

**Backend & Frontend CMS:**

- [ ] **Team Management:** Role-Based Access Control (RBAC - Admin/Editor/Viewer).
- [ ] **Security:** Audit Logs (Activity History) & SSO (SAML Login).
- [ ] **Branding:** White-labeling (Custom Logo, Favicon, Subdomain).
- [ ] **Analytics:** Proof-of-Play reports with CSV Export.
- [ ] **Integrations:** Google Calendar, Tableau, API Keys, RS232 Command configuration.
- [ ] **Share Links:** Publicly share playlists via URL with password protection.
