# 🌍 HDI Insight

<div align="center">

### AI-Powered Human Development Index Prediction Platform

Predict, analyze, and explore **Human Development Index (HDI)** scores using Machine Learning, AI, and interactive visualizations.

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react)](https://react.dev)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org)
[![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://mongodb.com)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org)
[![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://stripe.com)
[![Gemini](https://img.shields.io/badge/Google_Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev)

<br>

## 🚀 Live Demo

### [https://hdi-insight.onrender.com](https://hdi-insight.onrender.com)

</div>

![HDI Insight Hero](frontend/public/hero-screenshot.png)

---

# 📖 About the Project

HDI Insight is a full-stack Machine Learning web application that predicts and analyzes the **Human Development Index (HDI)** of countries based on key socioeconomic indicators.

The application combines:
* 🤖 Machine Learning prediction
* 💬 Google Gemini AI chatbot
* 📊 Interactive analytics dashboard
* 🔐 Secure authentication
* 💳 Stripe payment integration
* 📜 Prediction history
* 📰 Educational development blog

Users can enter country statistics and instantly receive:
* HDI Score
* Development Category
* AI-generated Policy Recommendations
* Personalized Insights

---

# 🌍 What is HDI?

The **Human Development Index (HDI)** is a composite statistic developed by the **United Nations Development Programme (UNDP)** to measure a country's level of human development.

It evaluates three major dimensions:

❤️ **Health**
* Life Expectancy at Birth

🎓 **Education**
* Mean Years of Schooling
* Expected Years of Schooling

💰 **Standard of Living**
* Gross National Income (PPP) per Capita

Countries are classified into four development categories:
* 🟢 **Very High** (≥ 0.800)
* 🟡 **High** (0.700 – 0.799)
* 🟠 **Medium** (0.550 – 0.699)
* 🔴 **Low** (< 0.550)

---

# ✨ Features

* 🤖 AI-powered HDI Prediction
* 📊 Interactive Dashboard
* 💬 Google Gemini AI Chatbot
* 📜 Prediction History
* 🔐 JWT Authentication
* 🔒 Password Encryption using bcrypt
* 💳 Stripe Credit System
* 📰 Development Blog
* 📱 Fully Responsive Design
* ⚡ FastAPI ML Microservice
* ☁ MongoDB Cloud Storage

---

# 🏗️ System Architecture

```text
                    User
                      │
                      ▼
            React + Vite Frontend
                      │
                 REST API
                      │
                      ▼
            Node.js + Express Backend
             │                  │
             ▼                  ▼
       MongoDB Atlas       Stripe API
             │
             ▼
        FastAPI ML Service
             │
             ▼
   Linear Regression Prediction Model
```

---

# 🛠️ Tech Stack

### Frontend
* React, Vite, React Router DOM, Axios, Lucide React

### Backend
* Node.js, Express.js, MongoDB, Mongoose, JWT, bcryptjs, Stripe API

### Machine Learning
* Python, FastAPI, Scikit-learn, Pandas, NumPy, Joblib

### AI
* Google Gemini API

---

# 📂 Project Structure

```text
hdi-insight/
│
├── frontend/             # React app
│   ├── src/
│   │   ├── components/   # UI components
│   │   ├── pages/        # App routes
│   │   └── services/     # API client
│   └── public/
│
├── backend/              # Node.js/Express App
│   ├── controllers/      # API logic
│   ├── models/           # Mongoose schemas
│   ├── routes/           # Express endpoints
│   └── server.js         # Entry point
│
└── ml-engine/            # FastAPI App
    ├── api/              # FastAPI routes
    ├── data/             # Training data
    ├── models/           # Saved .pkl ML models
    ├── src/              # ML training scripts
    └── requirements.txt
```

---

# 🚀 Installation

## 1️⃣ Setup ML Engine

```bash
cd ml-engine
python -m venv venv
```

**Activate**
* Windows: `.\venv\Scripts\activate`
* Mac/Linux: `source venv/bin/activate`

**Install & Run**
```bash
pip install -r requirements.txt
uvicorn api.main:app --reload --host 127.0.0.1 --port 8000
```

---

## 2️⃣ Setup Backend

```bash
cd backend
npm install
```

**Create `.env` file** in the `backend/` folder:
```env
PORT=5000
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_secret
STRIPE_SECRET_KEY=your_key
STRIPE_WEBHOOK_SECRET=your_secret
GEMINI_API_KEY=your_key
ML_API_URL=http://127.0.0.1:8000
FRONTEND_URL=http://localhost:5173
```

**Run**
```bash
npm run dev
```

---

## 3️⃣ Setup Frontend

```bash
cd frontend
npm install
```

**Create `.env` file** in the `frontend/` folder:
```env
VITE_API_URL=http://localhost:5000/api
```

**Run**
```bash
npm run dev
```
Open `http://localhost:5173` in your browser.

---

# 🔌 API Endpoints

| Method | Endpoint                                | Description             |
| ------ | --------------------------------------- | ----------------------- |
| POST   | `/api/auth/register`                    | Register User           |
| POST   | `/api/auth/login`                       | Login                   |
| POST   | `/api/predict`                          | Predict HDI             |
| GET    | `/api/history`                          | User Prediction History |
| POST   | `/api/chat`                             | AI Chatbot              |
| POST   | `/api/payments/create-checkout-session` | Stripe Checkout         |
| GET    | `/api/payments/verify-session`          | Verify Payment          |
| GET    | `/api/blog`                             | Fetch Blogs             |

---

# 🧠 Machine Learning Model

### Algorithm
✅ **Linear Regression**

### Input Features
* Life Expectancy
* Mean Years of Schooling
* Expected Years of Schooling
* Gross National Income (PPP)

### Output
* HDI Score
* Development Category
* Policy Recommendations

---

# 📄 License

This project is licensed under the **MIT License**.

---

<div align="center">

### ⭐ If you found this project helpful, consider giving it a Star!

Made with ❤️ by **Shaik Abdul Hanif**

</div>
