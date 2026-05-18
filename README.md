# Orbit

## Team Name

Team Synapse

## Problem Statement

College students often struggle with stress, anxiety, loneliness, and burnout, yet many hesitate to seek help due to stigma, lack of accessibility, or the absence of a supportive community. Existing wellness solutions can feel impersonal, overwhelming, or disconnected from students’ day-to-day experiences.

Orbit aims to solve this problem by creating a safe, engaging, and student-focused digital wellness ecosystem that combines AI companionship, habit-building missions, emotional tracking, and anonymous peer support.

## Team Members

* Anjali Yadav
* Vania Colaco
* Dueala Noronha
* Vaishnavi Nayak

## Project Description

Orbit is a polished, student-focused wellness application designed to support mental health and community engagement through AI-driven companionship, daily missions, and anonymous social interactions.

The platform provides students with a personalized wellness journey through an empathetic AI companion, gamified progress tracking, and community-driven support systems. Orbit combines modern UI/UX principles with AI-powered emotional assistance to create a safe, motivating, and accessible mental wellness experience.

---

# 🌟 Key Features

### Nova AI Companion

A personal AI guide powered by Google Gemini, providing empathetic support, wellness tracking, and meaningful conversations.

### Mood Hub

Track emotional well-being through intuitive mood check-ins and monitor progress over time.

### Daily Missions

Interactive and actionable wellness challenges designed to build healthy habits and improve student morale.

### Support Hub

An anonymous community space where students can share experiences, seek advice, and support one another safely.

### Avatar Personalization

Create and customize a digital avatar to represent your wellness journey.

### Orb Island

A gamified visual representation of personal growth, mood, and wellness progress.

### Profile & Progress

Comprehensive tracking of mission completions, activity, wellness stats, and overall engagement.

---

# 🛠️ Tech Stack

## Frontend

* React 19 (Vite)
* React Router 7
* Tailwind CSS v4
* Motion (Framer Motion)
* Lucide React

## Backend

* Firebase Authentication
* Firebase Firestore

## Database / Realtime

* Supabase

## APIs

* Google Gemini API (`@google/genai`)
* Eleven Labs API
* SupaBase

---

# 📁 Project Structure

```bash
src/
 ├── components/      # Reusable UI components
 ├── screens/         # Individual application pages
 ├── lib/             # Firebase & Supabase setup
 ├── data/            # Static data and configurations
 └── assets/          # Images and media assets

public/
 └── avatars/         # Avatar assets and static images
```

---

# 🚀 Installation Steps

## 1. Prerequisites

Make sure the following are installed/configured:

* Node.js (Latest LTS Recommended)
* Firebase Project
* Supabase Project
* Gemini API Key

---

## 2. Clone the Repository

```bash
git clone https://github.com/anjalio5/Synapse-Orbit-PS-8
cd path
```

---

## 3. Install Dependencies

```bash
npm install
```

---

## 4. Environment Configuration

Create a `.env` file in the root directory:

```env
GEMINI_API_KEY="your_gemini_api_key"
APP_URL="http://localhost:3000"
VITE_SUPABASE_URL="your_supabase_url"
VITE_SUPABASE_ANON_KEY="your_supabase_anon_key"
```

---

## 5. Firebase Setup

Update the `firebase-applet-config.json` file with your Firebase project credentials.

Enable:

* Anonymous Authentication
* Google Authentication
* Firestore Database

---

## 6. Run the Application

```bash
npm run dev
```

The application will run locally at:

```bash
http://localhost:3000
```

---

# 📖 Usage Instructions

1. Launch the Orbit application.
2. Sign in anonymously or using Google Authentication.
3. Complete onboarding and personalize your avatar.
4. Interact with Nova AI Companion for emotional support and guidance.
5. Track moods daily using Mood Hub.
6. Complete Daily Missions to build positive habits.
7. Participate anonymously in Support Hub discussions.
8. Monitor growth and achievements through Orb Island and Profile Progress.

---

# 🎥 Demo Links

```txt
https://orbitapp2026.netlify.app
https://orbit-pulse.netlify.app/
```

---

# 🔮 Future Scope

* AI-driven personalized wellness recommendations.
* Voice-based interaction with Nova AI.
* Community moderation using AI safety systems.
* Institution-level analytics dashboards for counselors.
* Wearable integration for real-time wellness tracking.
* Expanded gamification and reward systems.
* Multilingual support for accessibility.
* Push notifications and smart wellness reminders.

---

# 📜 Development Notes

* The application follows a modern Swiss-inspired design aesthetic with a warm and approachable color palette.
* Optimized for mobile-first usage with a native-app-like experience.
* AI interactions and mood analysis are processed efficiently for responsiveness and privacy.

---

# 🛡️ Privacy & Security

* Anonymous onboarding via Firebase Anonymous Authentication.
* Secure authentication and cloud data management.
* Community interactions designed to preserve student anonymity.
* Privacy-focused AI interaction workflows.

---

# 💡 Why Orbit?

Orbit is more than just a wellness app — it is a digital companion ecosystem designed specifically for students. By combining emotional support, gamification, AI assistance, and community interaction, Orbit creates an engaging and safe environment that encourages students to prioritize mental well-being every day.
