# 🚀 MissionPulse

> A real-time telemetry monitoring system that simulates spacecraft data, detects anomalies, and displays system health through an interactive mission control dashboard — built to one day be a public web experience for space enthusiasts.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-green?style=flat-square&logo=fastapi)
![React](https://img.shields.io/badge/React-18+-61DAFB?style=flat-square&logo=react)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange?style=flat-square&logo=scikit-learn)
![License](https://img.shields.io/badge/license-MIT-lightgrey?style=flat-square)

---

## 📖 Overview

MissionPulse simulates spacecraft telemetry streams — including temperature, battery voltage, and signal strength — and analyzes incoming data in real time to detect unusual behavior using machine learning.

The long-term vision is a **publicly accessible mission control experience** inspired by real programs like Artemis and OSIRIS-REx, where anyone can visit the site, watch live simulated telemetry, track system health, and feel what it's like to monitor a spacecraft in flight.

---

## ✨ Features

- 🛰️ **Telemetry Simulation** — Generates realistic spacecraft sensor data (battery, temperature, signal strength, and more)
- 🤖 **Anomaly Detection** — Machine learning pipeline identifies irregular patterns automatically
- 🚨 **Alert System** — Severity-tiered alerts triggered by detected anomalies
- 💚 **System Health Score** — Composite health indicator derived from all active sensor conditions
- 📊 **Live Dashboard** — Interactive charts and real-time system status panels
- 🌍 **Public Web Experience** *(in progress)* — Designed to be visited and explored by anyone, no setup required
- 🛸 **Multi-Spacecraft Support** *(planned)* — Monitor multiple missions simultaneously

---

## 🏗️ Architecture
```
Simulator → API → Anomaly Detection → Database → Dashboard
```
```
[ Telemetry Simulator ]
        ↓
[ FastAPI Backend ] ←→ [ SQLite via SQLAlchemy ]
        ↓
[ scikit-learn Anomaly Detector ]
        ↓
[ React Dashboard (Recharts / Chart.js) ]
```

---

## 🧰 Tech Stack

### Backend
| Tool | Purpose |
|------|---------|
| Python | Core language |
| FastAPI | REST API framework |
| SQLAlchemy | ORM / database layer |
| SQLite | Lightweight persistent storage |

### Machine Learning
| Tool | Purpose |
|------|---------|
| NumPy | Numerical computing |
| Pandas | Data manipulation |
| scikit-learn | Anomaly detection models |

### Frontend
| Tool | Purpose |
|------|---------|
| React | UI framework |
| Recharts / Chart.js | Data visualization |

### Deployment *(planned)*
| Tool | Purpose |
|------|---------|
| Render / Railway | Backend hosting |
| Vercel | Frontend hosting |
| PostgreSQL | Production database (replaces SQLite) |
| Docker | Containerization |

---

## 📁 Project Structure
```
missionpulse/
├── backend/
│   └── app/
│       ├── main.py           # App entry point
│       ├── models.py         # Database models
│       ├── schemas.py        # Pydantic schemas
│       ├── database.py       # DB connection setup
│       ├── routes/           # API route handlers
│       └── services/         # Business logic & ML services
├── frontend/
│   └── src/
│       ├── components/       # Reusable UI components
│       └── pages/            # Dashboard views
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+

### Backend
```bash
cd backend
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

API will be available at `http://localhost:8000`  
Interactive docs at `http://localhost:8000/docs`

### Frontend
```bash
cd frontend
npm install
npm run dev
```

Dashboard will be available at `http://localhost:5173`

---

## 🔬 How It Works

1. **Simulate** — The telemetry simulator generates continuous sensor readings for a spacecraft
2. **Detect** — The ML anomaly detector flags unusual patterns (e.g. sudden temperature spikes, battery drops, signal loss)
3. **Alert** — Triggered anomalies create severity-graded alerts stored in the database
4. **Visualize** — The React dashboard polls the API and renders live charts, health scores, and alert feeds

---

## 🗺️ Roadmap

### Phase 1 — Core (Current)
- [ ] Telemetry simulation engine
- [ ] Anomaly detection pipeline
- [ ] REST API with FastAPI
- [ ] Basic React dashboard

### Phase 2 — Real-Time
- [ ] WebSocket support for live streaming data
- [ ] Multiple spacecraft views
- [ ] More advanced ML models (Isolation Forest, LSTM)

### Phase 3 — Public Launch
- [ ] Migrate SQLite → PostgreSQL for production
- [ ] Dockerize backend and frontend
- [ ] Deploy to Render (API) + Vercel (frontend)
- [ ] Custom domain — open to everyone, no sign-up required
- [ ] Simulated mission events tied to real programs (Artemis, etc.)

---

## 🌍 Vision

MissionPulse is built to be a fun, open space anyone can visit — no account, no sign-up, just drop in and watch the data fly. With programs like Artemis pushing back to the Moon and commercial spaceflight taking off, there's never been a better time to bring that excitement to the browser.

---

## 👨‍💻 Author

**Johan Rosa**  
>:3
---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

