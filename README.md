# 🎓 StudyPro — Smart Study Planner

An AI-powered full-stack productivity assistant for students. Solves modern problems like procrastination, burnout, inconsistent habits, poor revision planning, and overwhelming workloads.

---

## 🚀 Quick Start

### Prerequisites
- **Node.js** v16 or higher
- **npm** v8 or higher  
- **MongoDB** — either:
  - Local: Install from https://www.mongodb.com/try/download/community
  - Cloud (free): Sign up at https://www.mongodb.com/cloud/atlas

---

## 📁 Project Structure

```
smart-study-planner/
├── backend/              # Node.js + Express API
│   ├── models/           # Mongoose schemas
│   ├── routes/           # API route handlers
│   ├── middleware/        # JWT auth middleware
│   ├── .env.example      # Environment variables template
│   ├── server.js         # Main server entry
│   └── package.json
├── frontend/             # React application
│   ├── public/
│   ├── src/
│   │   ├── components/   # Sidebar, shared UI
│   │   ├── context/      # Auth context
│   │   ├── pages/        # All page components
│   │   └── utils/        # API client, constants
│   └── package.json
├── package.json          # Root scripts
└── README.md
```

---

## ⚙️ Setup Instructions

### Step 1 — Clone / Extract
```bash
cd smart-study-planner
```

### Step 2 — Configure Backend
```bash
cd backend
npm install
cp .env.example .env
```

Now edit `backend/.env`:
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/smart-study-planner
JWT_SECRET=change_this_to_a_long_random_string_at_least_32_chars
NODE_ENV=development
```

> **MongoDB Atlas users:** Replace MONGODB_URI with your Atlas connection string:
> `mongodb+srv://username:password@cluster.xxxxx.mongodb.net/smart-study-planner`

### Step 3 — Configure Frontend
```bash
cd ../frontend
npm install
```

Optional — create `frontend/.env`:
```env
REACT_APP_API_URL=http://localhost:5000/api
```

### Step 4 — Run the Application

**Option A: Run separately (recommended)**
```bash
# Terminal 1 — Backend
cd backend
npm start
# Server starts at http://localhost:5000

# Terminal 2 — Frontend
cd frontend
npm start
# App opens at http://localhost:3000
```

**Option B: Run together from root**
```bash
cd smart-study-planner
npm install
npm run dev
```

---

## ✅ Verify Setup

1. Open http://localhost:3000
2. Click "Sign up free" and create an account
3. You're in! Explore Dashboard, Planner, Focus Mode, etc.

Backend health check: http://localhost:5000/api/health

---

## 🎯 Features Overview

| Feature | Description |
|---|---|
| 🧠 AI Study Plan Generator | Auto-distributes tasks by deadline & daily hours |
| 🎯 Focus Mode (Pomodoro) | SVG timer with distraction tracking |
| 💚 Burnout Detection | Monitors weekly load vs. your goal |
| 🔥 Habit Builder | Streaks + 7-day calendar visualization |
| 📊 Analytics Dashboard | Bar, line, pie charts + PDF export |
| 🚨 Procrastination Tracker | Score + recovery tips |
| 📅 Interactive Calendar | Task deadlines + session markers |
| ⚡ Energy-Based Planner | Match tasks to your energy level |
| 🌙 Dark / Light Mode | Toggle in sidebar |
| 🔐 JWT Authentication | Secure signup/login/profile |

---

## 🛠️ Tech Stack

- **Frontend:** React 18, React Router v6, Recharts, React Hot Toast
- **Backend:** Node.js, Express, Mongoose
- **Database:** MongoDB
- **Auth:** JWT + bcrypt
- **PDF Export:** jsPDF
- **Fonts:** Syne (display), DM Sans (body)

---

## 🔑 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | /api/auth/register | Create account |
| POST | /api/auth/login | Login |
| GET | /api/auth/me | Get current user |
| PUT | /api/auth/profile | Update profile |
| GET | /api/tasks | Get all tasks |
| POST | /api/tasks | Create task |
| PUT | /api/tasks/:id | Update task |
| DELETE | /api/tasks/:id | Delete task |
| PATCH | /api/tasks/:id/complete | Mark complete |
| POST | /api/tasks/generate-plan | AI plan generator |
| POST | /api/sessions/start | Start study session |
| PUT | /api/sessions/:id/end | End session |
| GET | /api/sessions/burnout-check | Burnout analysis |
| GET | /api/habits | Get habits |
| POST | /api/habits | Create habit |
| PATCH | /api/habits/:id/check | Toggle habit day |
| GET | /api/analytics/overview | Analytics data |
| GET | /api/analytics/weekly | Weekly breakdown |
| POST | /api/feedback | Submit feedback |

---

## 🐛 Troubleshooting

**"MongoDB connection error"**
- Make sure MongoDB is running: `mongod --dbpath /data/db`
- Or use MongoDB Atlas and update MONGODB_URI in .env

**"Port 5000 already in use"**
- Change PORT in backend/.env to 5001
- Update REACT_APP_API_URL in frontend/.env accordingly

**"Cannot find module" errors**
- Run `npm install` inside both `/backend` and `/frontend` directories

**Blank screen on frontend**
- Check browser console for errors
- Ensure backend is running on port 5000
- Verify REACT_APP_API_URL matches your backend URL

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Credits

Built with ❤️ for students everywhere.
- React, Node.js, MongoDB, Express communities
- Recharts for beautiful data visualization
- jsPDF for report exports
- Google Fonts (Syne + DM Sans)

**Version:** 1.0.0  
**Last Updated:** 2025
