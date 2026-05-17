# 📦 KhatKhat: Futuristic P2P Logistics Intelligence
Github link : https://github.com/yashbavkar26/KhatKhat.git
Video demo link: https://drive.google.com/drive/folders/1917WBvnpLAsqiX_8jTwZYgJfpqREJLcH?usp=sharing

**KhatKhat** is a decentralized, peer-to-peer (P2P) logistics platform designed to revolutionize hyper-local deliveries through a dynamic relay network. By leveraging existing human movement patterns, KhatKhat enables lightning-fast, cost-effective, and secure deliveries across urban landscapes.

---

## 🚀 Key Features

- **Dynamic Relay Chain**: Parcels move through multiple "nodes" (verified carriers) to reach destinations faster and more efficiently.
- **AI Matching Engine**: Intelligent pairing of parcels with carriers based on proximity, route alignment, and trust scores.
- **Real-Time Command Center**: A futuristic admin dashboard for live tracking, fraud detection, and operational monitoring.
- **Secure Handover**: Multi-stage OTP verification ensures parcel security at every relay point.
- **Trust & Reputation System**: A comprehensive trust-scoring algorithm for both senders and carriers.
- **Razorpay Integration**: Automated escrow payments and carrier payouts.

---

## 🛠️ Tech Stack

### Mobile Application (`/KhatKhat_App`)
- **Framework**: React Native + TypeScript
- **State Management**: React Query + Context API
- **Real-Time**: Socket.io-client + Firebase Auth
- **Maps**: Google Maps SDK

### Backend Services (`/backend`)
- **Runtime**: Node.js + Express.js
- **Database**: Firebase Firestore (NoSQL)
- **Communications**: Twilio API (SMS & OTP)
- **Payments**: Razorpay Node SDK
- **Geospatial**: Google Maps API

### Admin Dashboard (`/admin_dashboard`)
- **Framework**: Next.js 14 (App Router)
- **Styling**: TailwindCSS + Framer Motion (Glassmorphism UI)
- **Analytics**: Recharts
- **Real-Time Data**: Firebase Firestore Listeners

### Landing Page (`/landing_page`)
- **Framework**: Next.js + TailwindCSS
- **Aesthetics**: High-end premium dark mode with interactive logistics visualizations.

---

## 📁 Project Structure

```text
KhatKhat/
├── KhatKhat_App/      # React Native mobile application (Customer & Agent)
├── admin_dashboard/   # Next.js admin control center
├── backend/           # Node.js API server & AI matching logic
└── landing_page/      # Promotional website & marketing assets
```

---

## 🛠️ Setup Instructions

### 1. Backend Setup
```bash
cd backend
npm install
# Configure .env with Firebase, Twilio, and Razorpay keys
npm start
```

### 2. Admin Dashboard Setup
```bash
cd admin_dashboard
npm install
# Configure .env.local with Firebase keys
npm run dev
```

### 3. Mobile App Setup
```bash
cd KhatKhat_App
npm install
# Ensure you have Android Studio / Xcode configured
npx react-native run-android # or run-ios
```

### 4. Landing Page Setup
```bash
cd landing_page
npm install
npm run dev
```

---

## 🔄 Operational Flow

1. **Parcel Booking**: A customer creates a parcel request via the mobile app.
2. **AI Matching**: The backend identifies the optimal route and matches the parcel with the closest verified carrier.
3. **Relay Logic**: If the destination is far, the system sets up relay points for handovers.
4. **Secure Handover**: Carrier-to-carrier or carrier-to-receiver handovers are verified via unique OTPs.
5. **Live Monitoring**: Admins monitor the entire journey in real-time through the Command Center.
6. **Payment Settlement**: Upon successful delivery, the escrow is released, and payouts are credited to carriers.

---

## 🎨 Design Philosophy

KhatKhat follows a **Futuristic Cinematic Aesthetic**—utilizing deep blacks, neon orange accents (#FF6600), glassmorphism, and smooth micro-interactions to create a premium, high-tech experience for all users.

---

## 🛡️ Security

- **ID Verification**: All carriers must submit verification documents before taking jobs.
- **Fraud Detection**: AI-powered anomaly detection for route deviations and suspicious activity.
- **Encrypted Comms**: Secure Socket.io and HTTPS channels for all data transfers.

---

*Developed for the Aavishkaar Hackathon.*
