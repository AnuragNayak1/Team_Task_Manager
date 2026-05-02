# 🚀 Ethara — Team Task Manager

<p align="center">
  A full-stack project management app for teams to manage tasks, members, and progress efficiently.
</p>

---

## 🔥 Badges

![Node.js](https://img.shields.io/badge/Backend-Node.js-green)
![Next.js](https://img.shields.io/badge/Frontend-Next.js-black)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-green)
![Status](https://img.shields.io/badge/Status-Active-success)

---

## ✨ Features

- 👤 User Authentication (JWT login/signup)
- 📁 Project Creation & Management
- 👥 Invite Team Members via Email
- ✅ Task Assignment with Priority & Status
- 📊 Dashboard with Analytics
- 🔐 Role-Based Access (Admin vs Member)

---

## 🧰 Tech Stack

| Layer       | Technology |
|------------|------------|
| Frontend   | Next.js, React, Tailwind CSS |
| Backend    | Node.js, Express |
| Database   | MongoDB (Mongoose) |
| Auth       | JWT |

---

## Repo layout

```
Ethara/
├── backend/     # Express — auth, projects, tasks, dashboard
├── frontend/    # Next.js app
└── README.md
```

---

## 📸 Screenshots

### 🔐 Login Page
![Login](./frontend/public/login.png)

### 📁 Projects Page
![Projects](./frontend/public/projects.png)

### 📊 Dashboard
![Dashboard](./frontend/public/dashboard.png)

### 📋 Task Board
![Tasks](./frontend/public/tasks.png)

### 👥 Members Page
![Members](./frontend/public/members.png)

---

### 1️⃣ Setup MongoDB
- Use MongoDB Atlas or local installation  
- Get your connection string  

---

## ⚙️ Setup & Run

### 📦 Backend

cd backend  
cp .env.example .env  

**Edit `.env`:**

MONGODB_URI=your_connection_string  
JWT_SECRET=your_secret  
FRONTEND_URL=http://localhost:3000  

### ▶️ Run Backend

npm install  
npm run dev  

Backend → http://localhost:5000  

---

### 🌐 Frontend

cd frontend  
npm install  
npm run dev  

Frontend → http://localhost:3000  

---

## 🌐 Deployment

### 🔹 Backend (Render)
- Root: backend  
- Build: npm install  
- Start: npm start  

### 🔹 Frontend (Vercel)
- Root: frontend  
- Environment Variable:  
BACKEND_URL=https://your-backend-url  

---

## 🚀 Live Demo

- 🌍 Frontend: https://team-task-manager-nine-fawn.vercel.app/  
- ⚙️ Backend: https://team-task-manager-kk21.onrender.com  

---

## 🔗 API

- Base URL: /api  

### Features
- Authentication  
- Projects  
- Tasks  
- Dashboard  

### Usage

Authorization: Bearer <token>  

---

## 🧠 Notes

- Passwords → bcryptjs  
- Authentication → JWT (valid ~7 days)  
- Role-based access control (Admin & Member)  


