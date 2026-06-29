# HDI Insight - Human Development Index Predictor

HDI Insight is a full-stack Machine Learning web application designed to predict and analyze Human Development Index (HDI) scores and classification categories based on four key indicators:
1. **Life Expectancy at Birth** (health)
2. **Mean Years of Schooling** (education)
3. **Expected Years of Schooling** (education)
4. **Gross National Income (GNI) per Capita** (economic standard of living)

The app features three main use cases (Very High, Medium/emerging, and Low development) to showcase predictions, provide custom insights, and track historical inputs.

---

## Architecture Overview

The system consists of three main parts:
1. **ML Engine** (`ml-engine/`):
   - Built with Python (pandas, scikit-learn, joblib).
   - Fast API microservice running on port `8000`.
   - Exposes model prediction endpoint `/predict` and health check `/health`.
2. **Backend API** (`backend/`):
   - Node.js + Express server running on port `5000`.
   - Mongoose (MongoDB) to persist predictions history.
   - Integrates with the ML Engine API to query predictions and log results.
3. **Frontend Dashboard** (`frontend/`):
   - React application built with Vite + Tailwind CSS / custom modern CSS.
   - Communicates with the Express backend to make predictions and display historical data.

---

## How to Run the Services

### 1. ML Engine (FastAPI)
First, set up a virtual environment and install requirements:
```bash
cd hdi-insight/ml-engine
python -m venv venv
.\venv\Scripts\Activate.ps1   # (Windows)
# or source venv/bin/activate  # (Mac/Linux)
pip install -r requirements.txt
```
To run the model pipeline (once dataset is placed at `ml-engine/data/hdi_dataset.csv`):
```bash
python run_pipeline.py
```
To start the FastAPI service:
```bash
uvicorn api.main:app --host 127.0.0.1 --port 8000 --reload
```

### 2. Express Backend
Make sure MongoDB is running and configure `.env` in `backend/`:
```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/hdi-insight
ML_API_URL=http://localhost:8000
```
Install dependencies and run:
```bash
cd hdi-insight/backend
npm install
npm run dev # runs with nodemon
```

### 3. React Frontend
Install dependencies and run:
```bash
cd hdi-insight/frontend
npm install
npm run dev
```
The React frontend will be accessible at the Vite default URL (typically http://localhost:5173).
