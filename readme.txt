Ethara — Team Task Manager
==========================

A small full-stack app for teams who want projects, tasks, and a simple
dashboard without juggling five different tools.

You sign up, create a project, invite people by email, and split work into
tasks with priorities and statuses. Admins run the project (members, all
tasks). Members see what is assigned to them and can move those tasks along.


What is inside
--------------

Frontend:  Next.js (React), Tailwind, charts for project stats
Backend:   Express REST API, JWT login
Database:  MongoDB (Mongoose) — users, projects, tasks

The UI talks to the API through /api on the same site in dev and on Vercel
(Next rewrites that path to your real API URL).


Repo layout
-----------

Ethara/
  backend/     Express — auth, projects, tasks, dashboard
  frontend/    Next.js app
  README.md
  readme.txt


Run it locally
--------------

1) MongoDB — local install or MongoDB Atlas; grab a connection string.

2) Backend

   cd backend
   cp .env.example .env
   Edit .env — set MONGODB_URI and JWT_SECRET (and FRONTEND_URL=http://localhost:3000 for CORS)
   npm install
   npm run dev

   API: http://localhost:5000 (or your PORT).

3) Frontend (another terminal)

   cd frontend
   npm install
   npm run dev

   App: http://localhost:3000

   Optional: in frontend/.env.local set BACKEND_URL=http://127.0.0.1:5000
   if the API is not on the default host.

Leave NEXT_PUBLIC_API_URL unset locally so the browser uses same-origin /api
(rewrites to Express).


Environment variables (cheat sheet)
------------------------------------

Backend (backend/.env — never commit real secrets)

  MONGODB_URI   — required
  JWT_SECRET    — required, long random string
  FRONTEND_URL  — browser origin(s) for CORS; comma-separated if several
                  (e.g. Vercel prod + preview)
  PORT          — optional (Render sets this for you)

Frontend (Vercel / .env.local)

  BACKEND_URL           — full URL of the API, no trailing slash
                          (used by Next rewrites for /api/*)
  NEXT_PUBLIC_API_URL   — only if the browser must call the API host
                          directly (then CORS on backend must allow your site)


Deploy (Render + Vercel)
------------------------

1) Render — Web service, root directory backend, build npm install,
   start npm start. Set MONGODB_URI, JWT_SECRET, FRONTEND_URL to your
   Vercel URL(s).

2) Vercel — Project root frontend, env BACKEND_URL = your Render API URL.
   Redeploy after changing it.

3) Put the exact Vercel origin in Render FRONTEND_URL so CORS works.

Health check on the API: GET /health

Example live URLs (replace with yours if different):

  Frontend: https://team-task-manager-nine-fawn.vercel.app/
  Backend:  https://team-task-manager-kk21.onrender.com


API in one sentence
---------------------

REST under /api — signup/login, projects and members, tasks per project,
dashboard stats. Send Authorization: Bearer <token> after login.


Tech notes (for contributors)
------------------------------

Passwords: bcryptjs. Tokens: jsonwebtoken (about 7 days). No refresh-token
flow — logout clears client storage. Role rules (admin vs member) are
enforced in the API, not only in the UI.
