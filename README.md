# Vigilant Response (monorepo)

This repository contains the frontend and (optionally) backend for the Vigilant Response project.

Repository layout
- `frontend/` — Vite + React + TypeScript frontend (current contents).
- `backend/` — (optional) backend service (Node/Express, Python, etc.).
- `.github/workflows/` — CI workflows for build/test.

Quick start (frontend)
1. Open a terminal at the repo root and run:

```bash
cd frontend
npm install
npm run dev
```

2. Open the dev server (Vite default): http://localhost:5173

Running the backend (if present)
1. Open the `backend/` folder in another terminal and follow its README or run:

```bash
cd backend
npm install
npm run dev
```

Run both locally
- Use two terminals (one for `frontend`, one for `backend`). To run both with a single command, consider using `concurrently` or a root workspace script.

CI (GitHub Actions)
- The repo has a workflow at `.github/workflows/ci.yml` that:
  - builds the frontend (`frontend/`), runs its tests if present
  - attempts to build/test the backend only if `backend/package.json` exists

Add a backend
- Create a `backend/` folder and add your backend code there. The CI will pick it up automatically.

Notes
- This repo is intentionally split so frontend and backend can have independent lifecycles.
- If you prefer a workspace-based setup (`npm workspaces` / `pnpm`), I can add a root `package.json` and workspace config.
# Vigilant Response

## Backend Setup

1. Create a `.env` file in the project root using `.env.example` as reference.
2. Set your MySQL credentials in `.env`:

```env
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=DisasterAlertSystem
```

3. Start the backend:

```bash
npm run server
```

If credentials are incorrect, the server now exits with a clear error and prints the connection parameters it attempted.

## Frontend

Run the Vite app:

```bash
npm run dev
```
