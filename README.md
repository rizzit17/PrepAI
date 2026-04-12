# PrepAI

<p align="center">
  <b>AI-powered mock interview simulator for students and early-career job seekers.</b>
</p>

<p align="center">
  Practice role-specific interviews, get instant AI feedback, track your progress, and level up your prep.
</p>

---

## Overview

**PrepAI** is a full-stack mock interview platform built to help users prepare for technical and behavioral interviews in a more interactive and personalized way.

Users can choose a target role, select interview type and difficulty, answer AI-generated questions, and receive structured feedback with scoring, strengths, improvement areas, and model answers.  
The app also stores previous sessions so users can review their progress over time.

This project was built by **Rishit** as a portfolio-ready product combining modern frontend development, AI integration, authentication, and cloud data storage.

---

## Features

- Role-based interview generation
- Technical, Behavioral, and Mixed interview modes
- Difficulty selection: Rookie, Warrior, Legend
- AI-powered answer scoring and feedback
- Per-question breakdown with model answers
- Session history with saved results
- Google Sign-In with Firebase Authentication
- Firestore-based persistence
- Responsive UI with a gamified pixel-RPG inspired design
- Built with reusable React components and clean project structure

---

## Tech Stack

### Frontend
- React
- Vite
- Tailwind CSS
- React Router DOM

### Backend / Services
- Groq API (`llama-3.3-70b-versatile`)
- Firebase Authentication
- Firebase Firestore

### UI / Utilities
- lucide-react
- react-hot-toast

### Deployment
- Vercel

---

## Screenshots

Add screenshots here after deployment.

```md
![Landing Page](./screenshots/landing.png)
![Interview Screen](./screenshots/interview.png)
![Results Page](./screenshots/results.png)
Folder Structure
bash

prepai/
├── public/
├── src/
│   ├── components/
│   ├── context/
│   ├── hooks/
│   ├── lib/
│   ├── pages/
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css
├── .env.example
├── package.json
├── tailwind.config.js
└── vite.config.js
Environment Variables
Create a .env file in the root directory and add:

env

VITE_GROQ_API_KEY=your_groq_api_key_here
VITE_FIREBASE_API_KEY=your_firebase_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id
Getting Started
1. Clone the repository
bash

git clone https://github.com/rizzit17/PrepAI.git
cd PrepAI
2. Install dependencies
bash

npm install
3. Add environment variables
Create a .env file using .env.example.

4. Run the development server
bash

npm run dev
5. Build for production
bash

npm run build
Firebase Setup
To enable authentication and session storage:

Create a Firebase project
Enable Google Sign-In in Firebase Authentication
Create a Firestore database
Add the required Firebase config values to .env
Firestore Rules
js

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /sessions/{sessionId} {
      allow create: if request.auth != null && request.auth.uid == request.resource.data.uid;
      allow read, update, delete: if request.auth != null && request.auth.uid == resource.data.uid;
    }
  }
}
AI Prompting Flow
PrepAI uses structured prompting with the Groq API for:

generating interview questions
evaluating answers
scoring performance
returning strengths, weaknesses, tips, and model answers
This allows the app to provide fast and consistent mock interview feedback in a clean JSON-driven workflow.

Resume Description
One-liner
AI-powered mock interview simulator with role-specific question generation, real-time answer scoring, and session history — built with React, Groq LLaMA, and Firebase.

Resume Bullets
Built a full-stack mock interview platform supporting multiple job roles with AI-generated, difficulty-adjusted questions
Engineered a structured JSON prompting system for answer evaluation across relevance, depth, clarity, and examples
Implemented Firebase Authentication and Firestore persistence for secure user sign-in and session history tracking
Designed a responsive gamified interface to make interview preparation more engaging and interactive
Future Improvements
Voice mode for spoken answers
Coding interview mode with embedded editor
Daily streak tracker
Shareable result card
Leaderboard and comparative analytics
Secure backend proxy for Groq API in production
Author
Rishit
Built as a personal full-stack project to make interview preparation more interactive, intelligent, and engaging.

GitHub: rizzit17
License
This project is open for learning, inspiration, and portfolio demonstration.


