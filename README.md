<div align="center">

# 🎓 Cloud-Based Placement Management and Recruitment System

**A full-stack campus placement platform connecting Students, Placement Officers, and Corporate Recruiters.**

![React](https://img.shields.io/badge/Frontend-React%2018%20%2B%20Vite-61DAFB?logo=react&logoColor=white)
![Flask](https://img.shields.io/badge/Backend-Flask%20(Python%203.12)-000000?logo=flask&logoColor=white)
![MongoDB](https://img.shields.io/badge/Database-MongoDB%20Atlas-47A248?logo=mongodb&logoColor=white)
![Render](https://img.shields.io/badge/Deploy-Render-46E3B7?logo=render&logoColor=black)

</div>

---
## Live URL :  https://frontend-opal-tau-kjcer8fkaw.vercel.app/

## 👥 Created By

| # | Name |
| :-: | :--- |
| 112 | **Nikhil Lanje** |
| 125 | **Rutik Harbale** |
| 155 | **Aditya Bandewar** |
| 158 | **Rushikesh Kadam** |

---

## 📑 Table of Contents

- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [Technology Stack](#️-technology-stack)
- [Directory Structure](#-directory-structure)
- [Demo Credentials](#-demo-credentials)
- [Environment Variables](#️-environment-variables)
- [Local Development Setup](#-local-development-setup)
- [MongoDB Atlas Setup](#-mongodb-atlas-setup)
- [Render Deployment](#-render-deployment)
- [Security Best Practices](#-security-best-practices)

---

## 📖 About the Project

A complete, production-ready campus placement application built for colleges and universities. It streamlines the recruitment ecosystem by bringing together **Students**, **Placement Officers (Admins)**, and **Corporate Recruiters** on a single cloud-hosted platform, with automatic eligibility checking, pipeline tracking, interview scheduling, and live analytics.

---

## 🌟 Key Features

### 👨‍🎓 Student Role
- **Authentication**: Register, log in, and keep a secure JWT-based persistent session.
- **Detailed Profile Management**: Edit personal info, academic info (10th/12th/Diploma %, CGPA, active & total backlogs), skills, projects, certifications, and resume URL.
- **Live Profile Completeness**: Real-time completeness gauge (0–100%).
- **Placement Drives Catalog**: Search and filter opportunities by role, company, location, CTC, and branch.
- **Automatic Eligibility Checker**: Instant evaluation of CGPA, backlogs, branch, and 10th/12th scores against job requirements, with a detailed failure breakdown.
- **One-Click Applications**: Apply to eligible drives instantly.
- **Visual Progress Stepper**: Track the pipeline: `Applied` ➔ `Shortlisted` ➔ `Assessment` ➔ `Technical Interview` ➔ `HR Interview` ➔ `Selected`.
- **Interview Schedule**: View assessment/interview slots with date, time, and Google Meet link.
- **In-App Notifications**: Real-time notification drawer with unread count badge.

### 🛡️ Placement Officer / Admin Role
- **Analytics Dashboard**: Live metrics for total students, registered accounts, approved companies, active drives, total placed, placement %, and CTC averages.
- **Interactive Recharts Analytics**:
  1. Branch-wise placement distribution (Bar Chart)
  2. Top company selections (Horizontal Bar Chart)
  3. Monthly application trends (Area Chart)
  4. Recruitment pipeline stage breakdown (Pie Chart)
  5. Salary package distribution (Range Chart)
- **Company Approvals**: Review recruiter registrations and approve/reject company accounts before they can post drives.
- **Placement Drive Creator**: Modal builder for job openings with mandatory eligibility thresholds.
- **Student Directory**: Searchable student table with CGPA and backlog metrics.
- **Global Pipeline Manager**: Update candidate status stages across all drives.

### 🏢 Recruiter / Corporate Role
- **Company Account Registration**: Register a company profile (pending admin approval).
- **Opportunity Posting**: Create drive postings with role description, CTC, and eligibility criteria.
- **Applicant Evaluation**: Filter eligible applicants, view resume links, and update recruitment stages.
- **Interview Scheduler**: Schedule assessment and interview rounds (date, time, meeting link, candidate instructions) with automated student notifications.

---

## 🛠️ Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend** | React 18, Vite, Tailwind CSS, React Router DOM, Axios, Lucide React Icons, Recharts |
| **Backend** | Python 3.12, Flask, Flask-CORS, PyMongo, PyJWT, bcrypt, Gunicorn |
| **Database** | MongoDB Atlas (`placement_db`) |
| **Deployment** | Render (separate Frontend & Backend services) |

---

## 📁 Directory Structure

```text
Cloud Project/
├── README.md
├── .gitignore
├── backend/
│   ├── app.py                 # Main Flask application & Blueprints
│   ├── seed.py                # Database seed script for MongoDB Atlas
│   ├── config.py              # Configuration & Environment loader
│   ├── db.py                  # PyMongo client manager & Index creator
│   ├── Procfile               # Production startup command for Render
│   ├── requirements.txt       # Python dependencies
│   ├── .env.example           # Backend environment template
│   ├── middleware/
│   │   └── auth.py            # JWT authentication & Role authorization
│   ├── utils/
│   │   ├── eligibility.py     # Automatic eligibility checking engine
│   │   └── helpers.py         # ObjectId & BSON JSON formatters
│   └── routes/
│       ├── auth.py
│       ├── student.py
│       ├── company.py
│       ├── job.py
│       ├── application.py
│       ├── interview.py
│       ├── notification.py
│       └── admin.py
└── frontend/
    ├── package.json
    ├── vite.config.js
    ├── tailwind.config.js
    ├── index.html
    ├── .env.example
    └── src/
        ├── index.css
        ├── main.jsx
        ├── App.jsx
        ├── context/
        │   ├── AuthContext.jsx
        │   └── NotificationContext.jsx
        ├── services/
        │   └── api.js
        ├── components/
        │   └── common/        # Navbar, Sidebar, EligibilityBadge, ApplicationStepper, StatCard
        └── pages/
            ├── LandingPage.jsx
            ├── LoginPage.jsx
            ├── RegisterPage.jsx
            ├── student/       # Dashboard, Profile, Drives, Applications, Interviews
            ├── admin/         # Analytics, Students, Companies, Drives, Applications
            └── recruiter/     # Dashboard, Company, PostJob, Applicants
```

---

## 🔑 Demo Credentials

> These accounts are created by `python seed.py` and are for demo/testing only.

| Role | Email | Password | Description |
| :--- | :--- | :--- | :--- |
| **Placement Admin** | `admin@placement.edu` | `Admin@123` | Placement Director (full analytics & company approval) |
| **Student 1** | `student@placement.edu` | `Student@123` | Rahul Sharma (CSE, 8.8 CGPA, 0 backlogs, eligible) |
| **Student 2** | `ananya@placement.edu` | `Student@123` | Ananya Verma (IT, 7.9 CGPA, 0 backlogs) |
| **Student 3** | `vikram@placement.edu` | `Student@123` | Vikram Singh (ECE, 6.4 CGPA, 1 backlog, reduced eligibility) |
| **Recruiter** | `recruiter@techcorp.com` | `Recruiter@123` | TechCorp Solutions (approved corporate account) |

---

## ⚙️ Environment Variables

### Backend: `backend/.env`

```env
MONGO_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/placement_db?retryWrites=true&w=majority
JWT_SECRET=<a-long-random-secret>
PORT=5000
FRONTEND_URL=http://localhost:5173
```

### Frontend: `frontend/.env`

```env
VITE_API_URL=http://localhost:5000/api
```

> ⚠️ Never commit real database credentials or secrets. Keep `.env` in `.gitignore` and share only `.env.example`.

---

## 🚀 Local Development Setup

### Prerequisites
- Python 3.12+
- Node.js 18+ and npm
- A MongoDB Atlas cluster (see [below](#-mongodb-atlas-setup))

### 1. Backend

```bash
cd backend
pip install -r requirements.txt
python seed.py     # populate demo data in MongoDB Atlas
python app.py      # start Flask dev server
```

The API runs at `http://localhost:5000`.

### 2. Frontend

```bash
cd frontend
npm install
npm run dev
```

The web app runs at `http://localhost:5173`.

---

## 🌐 MongoDB Atlas Setup

1. Create a free cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Under **Database Access**, create a user with read/write permissions.
3. Under **Network Access**, add `0.0.0.0/0` to allow connections from Render.
4. Copy your SRV connection string:
   `mongodb+srv://<username>:<password>@cluster.mongodb.net/placement_db?retryWrites=true&w=majority`
5. Use it as `MONGO_URI` in your local `.env` and in the Render backend environment.

---

## ☁️ Render Deployment

### Service 1: Backend Web Service (Flask API)

| Setting | Value |
| :--- | :--- |
| Root Directory | `backend` |
| Environment | `Python 3` |
| Build Command | `pip install -r requirements.txt` |
| Start Command | `gunicorn app:app` |

**Environment variables:** `MONGO_URI`, `JWT_SECRET`, `FRONTEND_URL` (e.g. `https://placement-frontend.onrender.com`)

### Service 2: Frontend Static Site (React + Vite)

| Setting | Value |
| :--- | :--- |
| Root Directory | `frontend` |
| Build Command | `npm run build` |
| Publish Directory | `dist` |

**Environment variables:** `VITE_API_URL` (e.g. `https://placement-backend.onrender.com/api`)

---

## 🔒 Security Best Practices

- Passwords are hashed with **bcrypt** salt routines.
- Protected endpoints enforce authentication and role authorization middleware (`@jwt_required`, `@role_required`).
- Strict CORS configuration between frontend and backend.
- MongoDB connection strings and JWT secrets are managed only through environment variables.

---

<div align="center">

Made with ❤️ by **Nikhil Lanje**, **Rutik Harbale**, **Aditya Bandewar** and **Rushikesh Kadam**

</div>
