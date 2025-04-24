# SmartReview

**Elevator Pitch:** SmartReview: an AI-powered spaced-repetition web app combining FSRS scheduling with SBERT semantic clustering to personalize and optimize your study sessions effortlessly.

---

## Table of Contents
- [Description](#description)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [API Endpoints](#api-endpoints)
- [Usage](#usage)
- [Folder Structure](#folder-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Description
SmartReview is an AI-driven spaced-repetition prototype that leverages the FSRS scheduler and SBERT semantic clustering to deliver personalized study sessions. Built with FastAPI for the backend and React for the frontend, SmartReview helps learners optimize retention with science-backed algorithms.

## Features
- **Accurate Scheduling:** Uses FSRS spaced-repetition algorithm for optimal review intervals.
- **Semantic Clustering:** Groups similar content via SBERT embeddings and KMeans.
- **Interactive UI:** React-based dashboard to review flashcards and track progress.
- **Notifications:** Predicts and notifies optimal study times.
- **Extensible:** Modular design for adding more clustering or scheduling methods.

## Tech Stack
- **Backend:** Python, FastAPI, FSRS, Sentence-Transformers, scikit-learn, Uvicorn
- **Frontend:** React, Create React App, Fetch API
- **Dev Tools:** Git, Docker (optional)

## Architecture
1. **Frontend (React):** Presents flashcards; on review, sends last review timestamp, ratings, and difficulty factor to backend.
2. **Backend (FastAPI):** Computes next review interval and notification timestamp using FSRS and circadian adjustment;
   also clusters cards for topic grouping.
3. **Scheduler (FSRS):** Samples next interval based on recall probability function.
4. **Clustering (SBERT + KMeans):** Generates semantic embeddings and groups cards.

## Getting Started

### Prerequisites
- Python 3.8+ and Node.js 14+
- pip and npm installed
- (Optional) Docker for containerization

### Backend Setup
```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate      # On Windows use `.venv\Scripts\activate`
pip install --upgrade pip
pip install fsrs sentence-transformers scikit-learn fastapi uvicorn python-dotenv
```

Add any environment variables to `.env` if needed.

To run the backend server:
```bash
uvicorn app:app --reload --host 0.0.0.0 --port 8000
```

Swagger docs available at [http://localhost:8000/docs](http://localhost:8000/docs).

### Frontend Setup
```bash
cd frontend
npm install
npm start
```

Frontend will be available at [http://localhost:3000](http://localhost:3000).

## API Endpoints

### `POST /next-review`
- **Request:** `{ last_review_ts: number, ratings: number[], q?: number }`
- **Response:** `{ next_review_ts: number, notification_ts: number }

### `POST /cluster`
- **Request:** `{ texts: string[], n_clusters?: number }`
- **Response:** `{ clusters: Record<string, number[]> }

## Usage
1. Open the frontend at `http://localhost:3000`.
2. Click on a card to reveal the answer, then "I Got It ✓" to submit your rating.
3. Receive your next review time in an alert or notification.

## Folder Structure
```
backend/
├── app.py
├── model.py
├── requirements.txt
└── .env

frontend/
├── package.json
├── public/index.html
└── src/
    ├── index.jsx
    ├── App.jsx
    └── components/
        ├── Dashboard.jsx
        └── ReviewCard.jsx
```

## Contributing
1. Fork the repository
2. Create a branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## License
This project is licensed under the [MIT License](LICENSE).

