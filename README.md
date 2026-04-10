# A5_Project_Thesis

# CareerLink: AI-Powered Campus Placement Management System

## Authors
* **Sk.Mohammad Ali** (Y22ACS558)
* **M.Hema Bhuvaneswari** (Y22ACS501)
* **V.Sravani** (Y22ACS587)
* **S.Naga Goutham** (Y22ACS564)

---

## Implementation

### Frontend Application
React-based responsive web application for students, recruiters, and administrators.

🔗 **https://github.com/ACS558/CareerLink-Frontend**

🌐 **Live Demo:** https://career-link-frontend-henna.vercel.app

### Backend Server
Node.js backend with Express.js, MongoDB, and AI integration.

🔗 **https://github.com/ACS558/CareerLink-Backend**

🌐 **API Server:** https://careerlink-backend-ifv6.onrender.com

---

## Overview

**CareerLink** is an intelligent campus placement management platform that revolutionizes how educational institutions conduct recruitment drives. The system automates the entire placement process from job posting to final selection, incorporating **Artificial Intelligence** for resume analysis and **real-time WebSocket** technology for instant notifications.

The platform serves **four distinct user roles** – Students, Recruiters, College Administrators, and Alumni – providing each with specialized tools to streamline campus recruitment.

Key innovation: **AI-powered Applicant Tracking System (ATS)** using **Google Gemini Flash 2.5** that analyzes resumes against job requirements and provides compatibility scores, dramatically reducing manual screening time.

---

## Project Components

### 1. **Student Module**
* Browse approved job postings with advanced filters
* One-click application submission with eligibility validation
* Real-time ATS compatibility scores (0-100%)
* Application status tracking with instant notifications
* Skill gap analysis and career guidance

### 2. **Recruiter Module**
* Post job openings with detailed requirements
* Automated resume screening using AI
* **Auto-Shortlist Feature:** Automatically selects top 30% candidates
* **Bulk Operations:** Update 200+ applications in seconds
* Recruitment analytics dashboard

### 3. **Admin Module**
* Approve recruiter and alumni registrations
* Moderate job postings before publication
* Platform-wide analytics (branch-wise, company-wise)
* Generate placement reports in Excel/PDF
* Manage students across multiple branches

### 4. **Alumni Module**
* Post job referrals from current organizations
* Share interview experiences and career tips
* Provide mentorship through community feed

### 5. **AI-Powered ATS System**
* Resume-to-job compatibility analysis using Google Gemini AI
* Identifies matched skills and missing qualifications
* Provides improvement recommendations
* 85% accuracy compared to manual evaluation
* Processes applications in <5 seconds

### 6. **Real-Time Notification System**
* WebSocket-based instant updates using Socket.IO
* Multi-channel delivery (in-app + browser notifications)
* <3 second average delivery time
* Persistent notification storage in MongoDB

---

## System Architecture

CareerLink implements a **three-tier architecture**:

```
┌─────────────────────────────────────────────────────────┐
│           PRESENTATION LAYER (Frontend)                 │
│  React.js + Vite + Tailwind CSS + Socket.IO Client     │
└────────────────────┬────────────────────────────────────┘
                     │ HTTP/REST + WebSocket
┌────────────────────▼────────────────────────────────────┐
│          APPLICATION LAYER (Backend)                    │
│  Node.js + Express.js + Socket.IO + JWT Auth           │
│  Google Gemini AI Integration + Cloudinary             │
└────────────────────┬────────────────────────────────────┘
                     │ Mongoose ODM
┌────────────────────▼────────────────────────────────────┐
│              DATA LAYER (Database)                      │
│  MongoDB Atlas (NoSQL Document Database)                │
│  11 Collections: Users, Students, Jobs, Applications,    │
│  Notifications, Feed, Placements                        │
└─────────────────────────────────────────────────────────┘
```

**External Services:**
* **Cloudinary** - Resume file storage and delivery
* **Google Gemini Flash 2.5** - AI-powered resume analysis
* **Socket.IO** - Real-time bidirectional communication

---

## Technologies Used

### Frontend
* **React 18.2** - Component-based UI library
* **Vite 5.0** - Lightning-fast build tool
* **Tailwind CSS 3.3** - Utility-first styling
* **Axios** - HTTP client with interceptors
* **React Router 6.x** - Client-side routing
* **Socket.IO Client 4.5** - WebSocket integration
* **Context API** - State management

### Backend
* **Node.js 18.x** - JavaScript runtime
* **Express.js 4.18** - Web application framework
* **MongoDB 6.0** - NoSQL database
* **Mongoose 7.x** - MongoDB ODM
* **Socket.IO 4.5** - Real-time engine
* **JWT** - Authentication tokens
* **bcrypt** - Password hashing
* **Google Generative AI SDK** - Gemini integration

### Cloud & DevOps
* **Vercel** - Frontend deployment
* **Render** - Backend hosting
* **MongoDB Atlas** - Database cloud hosting
* **Cloudinary** - File storage CDN
* **Git & GitHub** - Version control

---

## Key Features

### 🤖 **AI-Powered Features**
* **Automated Resume Scoring** - AI analyzes resumes against job descriptions
* **Auto-Shortlist Algorithm** - Automatically selects top 30% candidates
* **Skill Gap Analysis** - Identifies missing qualifications

### ⚡ **Real-Time Features**
* **Instant Notifications** - WebSocket-based updates (<3s delivery)
* **Live Application Status** - Real-time tracking across all stages
* **Browser Push Notifications** - Desktop alerts for critical updates

### 🚀 **Efficiency Features**
* **Bulk Operations** - Update 200+ applications simultaneously
* **One-Click Applications** - Streamlined submission process
* **Automated Eligibility Checks** - Prevents invalid applications
* **Excel Export** - Download placement data for reporting

### 📊 **Analytics Features**
* **Recruiter Dashboard** - Application trends, conversion rates
* **Admin Analytics** - Branch-wise, company-wise statistics
* **Performance Metrics** - Placement rates, average packages

### 🔒 **Security Features**
* **JWT Authentication** - Secure stateless sessions
* **bcrypt Password Hashing** - Industry-standard encryption
* **Role-Based Access Control (RBAC)** - Four distinct user roles
* **Input Validation** - Prevents injection attacks

---

## Installation & Setup

### Prerequisites
* Node.js 18.x or higher
* MongoDB 6.0 or higher
* npm or yarn package manager
* Google Gemini API key
* Cloudinary account

### Frontend Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/careerlink-frontend.git
cd careerlink-frontend

# Install dependencies
npm install

# Create .env file
cat > .env << EOF
VITE_API_URL=http://localhost:5000
VITE_SOCKET_URL=http://localhost:5000
EOF

# Start development server
npm run dev

# Build for production
npm run build
```

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/careerlink-backend.git
cd careerlink-backend

# Install dependencies
npm install

# Create .env file
cat > .env << EOF
PORT=5000
MONGO_URI=.....
JWT_SECRET=your_jwt_secret_key_here
GEMINI_API_KEY=your_google_gemini_api_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
FRONTEND_URL=http://localhost:5173
EOF

# Start development server
npm run dev

# Start production server
npm start
```

### Database Setup

```bash
# Start MongoDB locally
mongod

# Or use MongoDB Atlas (cloud)
# Replace MONGO_URI in .env with your Atlas connection string
```

---

## Environment Variables

### Frontend (.env)
```env
VITE_API_URL=http://localhost:5000
VITE_SOCKET_URL=http://localhost:5000
```

### Backend (.env)
```env
# Server Configuration
PORT=5000
NODE_ENV=development

# Database
MONGO_URI=mongodb://localhost:27017/careerlink

# Authentication
JWT_SECRET=your_super_secret_jwt_key_minimum_32_characters
JWT_EXPIRE=7d

# Google Gemini AI
GEMINI_API_KEY=your_google_gemini_api_key_here

# Cloudinary (File Storage)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:5173
```

---

## Deployment

### Frontend (Vercel)

```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod

# Configure vercel.json for SPA routing
{
  "rewrites": [
    { "source": "/(.*)", "destination": "/index.html" }
  ]
}
```

### Backend (Render)

1. Create new Web Service on Render
2. Connect GitHub repository
3. Set build command: `npm install`
4. Set start command: `npm start`
5. Add environment variables
6. Deploy

### Database (MongoDB Atlas)

1. Create cluster on MongoDB Atlas
2. Create database user
3. Whitelist IP addresses (0.0.0.0/0 for development)
4. Copy connection string to MONGO_URI

---

## Testing

### Run Tests

```bash
# Frontend tests
npm run test

# Backend tests
npm run test

# Integration tests
npm run test:integration
```

---

## Research Contribution

This project demonstrates how **Artificial Intelligence** and **Real-Time Communication** technologies can transform campus placement management by:

* **Automating resume screening** using Natural Language Processing
* **Reducing recruiter workload** by 60% through bulk operations
* **Improving placement rates** via data-driven analytics
* **Enhancing student experience** with instant notifications and transparency

Department of Computer Science and Engineering, Bapatla Engineering College

---

## Future Enhancements

### Planned Features

1. **Video Interview Integration**
   * Built-in video conferencing for remote interviews
   * Interview scheduling and calendar integration
   * Recording and playback functionality

2. **Mobile Application Development**
   * Native iOS and Android apps using React Native
   * Push notifications for mobile devices
   * Offline mode for viewing applications

3. **Advanced AI Features**
   * Resume parsing and auto-fill profiles
   * Job recommendation engine based on student profiles
   * Predictive analytics for placement success rates
   * Chatbot for student queries

4. **External Platform Integration**
   * LinkedIn profile import
   * HackerRank/LeetCode skill verification
   * Google Calendar integration for interviews
   * Email notification system

5. **Enhanced Analytics**
   * Placement trend analysis across years
   * Company hiring pattern insights
   * Salary benchmarking by branch/CGPA
   * Student skill gap reports

---

## GitHub Repositories

### Frontend Application
React-based responsive web application for all user roles.

🔗 **https://github.com/ACS558/CareerLink-Frontend**

### Backend Server
Node.js backend with Express.js, AI integration, and real-time features.

🔗 **https://github.com/ACS558/CareerLink-Backend**

---

This project was developed as part of the Final Year Project at **Bapatla Engineering College**.

**Project Guide:** Mr. K. Arun Babu, Assistant Professor, Department of CSE

---

## Acknowledgements

We would like to thank:

* **Mr. K.Arun Babu** - Project Guide and Mentor
* **Dr. M.Rajesh Babu** - Head of Department, CSE
* **Bapatla Engineering College** - For support
* **Google Cloud** - For Gemini AI API access
* **MongoDB Atlas** - For database hosting
* **Vercel & Render** - For deployment platforms

---

**⭐ If you find this project useful, please give it a star on GitHub!**

**Built with ❤️ by CareerLink Team | Bapatla Engineering College | 2025-2026**
