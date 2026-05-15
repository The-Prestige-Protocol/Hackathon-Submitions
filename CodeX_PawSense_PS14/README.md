# PawSense | Intelligent Animal Welfare

## Team Name
CodeX

## Problem Statement
PawSense is a comprehensive, AI-powered animal welfare platform and companion care ecosystem. It connects pet owners, animal lovers, and NGOs to create a safer and healthier environment for animals.

## Team Members
- Member 1
- Member 2
- Member 3

## GitHub Repository
https://github.com/SPB-6814/PresitgeProtocol_CodeX

## Demo Video
https://drive.google.com/file/d/10ux6LkIMidfvvb1nn1XuE6NEOXxLNCdu/view?usp=sharing

## Presentation Link

## Features
- Community & Rescue Platform (Next.js Frontend): Interactive map for animal rescue operations, home feed for community posts, wellness tracking, NGO dashboard, secure authentication.
- AI Cat Mood Detector (Computer Vision Backend): Analyzes feline body language using YOLOv8 pose estimation to classify moods into Friendly, Alert, Threatened, Hunting, and Relaxed.

## Tech Stack
- Frontend: Next.js, Tailwind CSS, Shadcn UI, Leaflet, Supabase
- Backend: Flask
- Database: Supabase
- AI/ML: Ultralytics YOLOv8, OpenCV, MediaPipe, NumPy

## Setup Instructions

### Prerequisites
- Node.js (v18+)
- Python (3.8+)
- A Supabase Project (for frontend auth/database)

### 1. Running the Next.js Frontend
Navigate to the `my_app` directory:
```bash
cd my_app
```

Install dependencies:
```bash
npm install
```

Set up your `.env` file with Supabase credentials:
```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

Start the development server:
```bash
npm run dev
```
The app will be available at `http://localhost:3000`.

### 2. Running the AI Mood Detector
Navigate to the `pet-wellness-cv` directory:
```bash
cd pet-wellness-cv
```

Install Python dependencies:
```bash
pip install -r requirements.txt
```

Run the Flask server:
```bash
python app.py
```
The AI server will download the YOLOv8 nano model on the first run and will be available at `http://localhost:5000`.
