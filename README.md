

## 🧠 What is SentiLog AI?

SentiLog AI is an open-source platform that combines news sentiment analysis and personal mood journaling. It features a modern React frontend, a robust Node.js/Express backend, and a Python/Flask microservice for ML-powered sentiment/emotion analysis.

---

## 🌟 Core Features

SentiLog AI provides a unique fusion of sentiment-aware news analysis and personal mental wellness tracking through the following key features:

### 📰 Real-Time News Bias Filter

- Automatically analyzes current news articles and classifies them based on political bias: Left, Right, or Neutral.
- Helps users recognize media bias and form balanced opinions.
- Uses Natural Language Processing (NLP) models to assess sentiment and ideological leaning in real-time.

### 📓 Daily Mood Journal

- Users can write daily journal entries about their thoughts or experiences.
- The system performs sentiment and emotion analysis (e.g., happy, sad, anxious).
- Helps users track their mental state over time, identifying patterns or triggers.
- Journal data can be cross-referenced with consumed news to understand the impact of external events on personal emotions.

---

## 📁 Project Structure

```
project-root/
│
├── client/ 
|   ├── index.html/
|   ├── public/                 
│   └── src/                 # React frontend (Vite + Tailwind)
│       ├── pages/           # JournalPage, NewsPage, Dashboard
│       ├── components/      # Navbar, SentimentCard, ChartPanel
│       ├── App.jsx
│       └── main.jsx
│
├── server/                  # Node.js + Express backend
│   ├── routes/              # journal.js, news.js
│   ├── controllers/
|   ├── middlewares/         # Express entry
|   ├── uploads/
|   ├── utils/
│   ├── models/              # Mongo schemas
│   └── index.js             
│
├── ml-api/                  # Flask-based ML service
│   ├── app.py
│   ├── model/
|   ├── vader_service.py/
│   └── requirements.txt
|
├── notebook/
|    ├── varder_sentiment_demo.ipynb
│    
├── .gitignore
├── README.md
└── package.json / envs
```

---

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/your-org/SentiLog-AI.git
cd SentiLog-AI
```

---

### 2. Setup the Frontend (client/)

```bash
cd client
npm install
npm run dev
```

- Built with [Vite](https://vitejs.dev/) + [React](https://react.dev/) + [Tailwind CSS](https://tailwindcss.com/)
- Main routes: `/journal`, `/news`, `/dashboard`
- Placeholder components: `Navbar`, `TextInput`, `SentimentCard`, `LineChart`

---

### 3. Setup the Backend (server/)

```bash
cd ../server
npm install
npm run dev
```

- [Express.js](https://expressjs.com/) API server
- Connects to MongoDB (see `.env.example`)
- Routes:
  - `POST /api/journal/analyze` → calls ML API
  - `POST /api/news/analyze` → calls ML API
- Uses [Mongoose](https://mongoosejs.com/) for MongoDB schemas

---

---

### 📘 API Documentation (Swagger)

Once your backend server is running, you can explore all API endpoints using **Swagger UI**:

[https://sentilog-ai.onrender.com/api-docs](https://sentilog-ai.onrender.com/api-docs)

This interactive documentation provides:

- Available endpoints and HTTP methods
- Required parameters and request formats
- Sample requests and responses
- Error status codes

> **Note:** If your server runs on a different port, update the URL accordingly (e.g., `http://localhost:3000/api-docs`).

### 4. Setup the ML API (ml-api/)

```bash
cd ../ml-api
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python app.py
```

- [Flask](https://flask.palletsprojects.com/) microservice
- `/predict` POST endpoint: accepts `{"text": "..."}` and returns mock sentiment/emotion

---

### 5. Environment Variables

- Copy `.env.example` in `server/` to `.env` and fill in your MongoDB URI and other secrets.

---


## 📦 Tech Stack

- **Frontend:** React, Vite, Tailwind CSS
- **Backend:** Node.js, Express, MongoDB, Mongoose
- **ML API:** Python, Flask, transformers, vaderSentiment

---

