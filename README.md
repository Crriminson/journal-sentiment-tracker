# 📔 Daily Journal Sentiment Tracker

> A beautiful web application that analyzes the emotional sentiment of your daily journal entries and visualizes your mood patterns over time.

**🔗 Live demo:** https://crriminson.github.io/journal-sentiment-tracker/

The web app runs entirely in your browser. Sentiment is scored with the AFINN lexicon (via [`sentiment`](https://www.npmjs.com/package/sentiment), which also handles negations like "not happy"), and entries are saved in your browser's local storage, so nothing leaves your device. The original Flask + TextBlob API is kept in `backend/` for reference.

---

## ✨ Features

- 📝 **Daily Journaling** - Write and save your thoughts
- 🧠 **Smart Analysis** - Automatic sentiment detection using AI
- 📊 **Mood Visualization** - Interactive charts showing your emotional journey
- 💾 **Data Persistence** - All entries securely saved
- 🎨 **Clean Interface** - Simple and intuitive design

---

## 🛠️ Tech Stack

| Frontend | Backend | Database | AI/ML |
|----------|---------|----------|-------|
| HTML/CSS/JS | Browser-only (live demo) | localStorage | AFINN lexicon (`sentiment`) |
| Chart.js | Python Flask (optional, `backend/`) | SQLite | TextBlob NLP |

---

## 🚀 Quick Start

Run the web app locally with any static server:

```bash
git clone https://github.com/Crriminson/journal-sentiment-tracker.git
cd journal-sentiment-tracker/frontend
python -m http.server 3000
# Visit: http://localhost:3000
```

### Optional: original Flask API

The steps below run the original Flask + TextBlob backend. The current frontend doesn't need it.

### 1️⃣ Setup
```bash
cd journal-sentiment-tracker/backend
```

### 2️⃣ Install Dependencies
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
python -m textblob.download_corpora
```

### 3️⃣ Launch Application
```bash
python app.py
```


---

## 📡 API Reference

### `POST /api/entries`
**Add a new journal entry**
```json
{
  "text": "I feel amazing today! 😊",
  "date": "2024-01-01"
}
```

### `GET /api/entries`
**Retrieve all entries with sentiment analysis**
```json
{
  "entries": [
    {
      "id": 1,
      "text": "I feel amazing today! 😊",
      "sentiment_score": 0.8,
      "sentiment_label": "positive"
    }
  ]
}
```

---

## 📁 Project Structure

```
📦 sentiment-tracker/
├── 🔧 backend/
│   ├── app.py              # Flask application
│   ├── database.py         # Database operations
│   └── requirements.txt    # Python dependencies
└── 🎨 frontend/
    ├── index.html         # Main interface
    ├── style.css          # Styling
    └── script.js          # Frontend logic
```

---

## 📦 Dependencies

```txt
flask
textblob
flask-cors
gunicorn
```

---

<div align="center">

**Made with ❤️ for tracking your emotional journey**

⭐ Star this repo if you found it helpful!

</div>
