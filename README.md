[README.md](https://github.com/user-attachments/files/32179836/README.md)
# TASKNOVA — AI-Powered Project Management & Study Productivity Platform

> **"Plan. Collaborate. Learn. Achieve."**

🌐 **Live Production Deployment**: [https://tasknova-platform.vercel.app](https://tasknova-platform.vercel.app)

TASKNOVA is an enterprise-grade full-stack platform that harmonizes professional project execution, real-time team collaboration, academic study planning, Pomodoro focus management, and AI copilots into a single high-velocity SaaS workspace.

---

## 🚀 Key Platform Capabilities

### 1. Project & Sprint Management
* **Interactive Kanban Board**: Drag-and-drop or click-to-move tasks across `TO DO`, `IN PROGRESS`, `IN REVIEW`, and `COMPLETED` columns with automatic project progress recalculations.
* **Multi-Project Tracking**: Manage multiple high-impact projects with milestones, priority tags (`Urgent`, `High`, `Medium`, `Low`), deadlines, and ownership.
* **Threaded Discussions & Reactions**: Real-time project comments with nested replies and emoji reaction toggles (`🚀`, `🔥`, `👍`, `❤️`).

### 2. Academic Study Hub & Research
* **Dynamic Study Planner**: Generate day-by-day exam revision schedules with weak-area diagnostics and topic time allocations.
* **Integrated Academic Search**:
  * **Open Library API**: Live textbook and author search with cover art retrieval.
  * **Crossref REST API**: Query millions of peer-reviewed journal papers and DOIs.
  * **YouTube Data API**: Educational lecture and technical tutorial search.
  * **Open-Meteo Weather API**: Environmental telemetry for optimal study conditions.
* **Focus Timer (Pomodoro)**: Configurable study sessions with ambient audio controls (Rain, White Noise, Forest, Cafe).

### 3. TASKNOVA AI Copilot (Powered by Google Gemini)
* **"What should I work on today?"**: Instant daily briefing analyzing active deadlines, high-priority tasks, and upcoming milestones for **SHIVAM SINGH**.
* **AI Project Breakdown**: Converts high-level product goals into structured engineering phases and actionable Kanban tasks with one-click task import!
* **Diagnostic Quiz Generator**: Generates 5 multiple-choice questions with explanations for rapid self-assessment.
* **Project Risk Analyzer**: Evaluates completion rate, critical path tasks, and team capacity to forecast delivery risks.

### 4. Security & Privacy
* **Role-Based Access Control (RBAC)**: Fine-grained permissions across `Owner`, `Admin`, `Project Manager`, `Editor`, `Contributor`, and `Viewer`.
* **Two-Factor Authentication (2FA)**: Authenticator App (TOTP) and Hardware Key support.
* **GDPR Portability**: Instant one-click user data export in clean JSON format.
* **Security Audit Trail**: Real-time logging of authentication events, device fingerprints, and permission changes.

---

## 🛠️ Tech Stack Architecture

* **Frontend**: React 19, TypeScript, Tailwind CSS v4, Lucide Icons, Vite.
* **Backend**: Node.js, Express, TypeScript (`tsx`).
* **Database & ORM**: SQLite (development/zero-config) & PostgreSQL-ready via Prisma ORM (28 relational models).
* **Authentication**: JSON Web Tokens (JWT) with bcrypt password hashing and RBAC middleware.
* **AI Engine**: Google Gemini API via official `@google/genai` SDK with built-in intelligent fallback.
* **File Uploads**: Multer with 25MB limits and MIME type whitelisting.

---

## 📦 Getting Started

### Prerequisites
* Node.js v18+ (tested on Node v24.20.0)
* npm v9+

### 1. Environment Configuration
Duplicate `.env.example` to `.env` (already configured with local development defaults):

```bash
cp .env.example .env
```

```env
PORT=5000
NODE_ENV=development
DATABASE_URL="file:./dev.db"
JWT_SECRET="tasknova-secure-jwt-super-secret-key-2026-production"
GEMINI_API_KEY="your_gemini_api_key_here" # Optional: AI uses intelligent fallback if unprovided
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Initialize Database & Seed Sample Data
```bash
# Push Prisma schema to SQLite
npm run db:push

# Generate Prisma Client
npm run db:generate

# Seed initial database with SHIVAM SINGH profile and projects
npm run db:seed
```

### 4. Run the Full-Stack Application
In two terminal tabs:

**Terminal 1 (Backend Server on port 5000):**
```bash
npm run server
```

**Terminal 2 (Frontend Client on port 3000):**
```bash
npm run dev
```

Visit **`http://localhost:3000`** in your browser.

---

## 🧪 Automated Testing

TASKNOVA includes an automated integration test suite verifying health checks, JWT authentication, project CRUD, task transitions, todos, comments, AI endpoints, and data export:

```bash
npm run test:api
```

All 15 integration tests run against an isolated test instance and report comprehensive pass/fail assertions.

---

## 👤 Default User Profile

* **Name**: `SHIVAM SINGH`
* **Role**: `Student & Project coordinator`
* **Email**: `shivam.singh@tasknova.app`
* **Password**: `Password@123`
* **Avatar**: Neutral blank avatar DP (Initials: `SS`)
* **Dashboard Greeting**: `"HELLO, SHIVAM 👋"`

---

## 📚 API Documentation
For detailed REST endpoints, request/response models, and status codes, see [docs/API.md](docs/API.md).
