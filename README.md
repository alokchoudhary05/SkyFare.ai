<div align="center">

# ✈️ SkyFare AI — Flight Price Prediction

**An end-to-end Machine Learning web application that predicts domestic flight prices in India using a Random Forest Regressor, served through a Flask REST API with a modern, responsive UI.**

[![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.1-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-3.0-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

</div>

---

## 📌 Overview

SkyFare AI helps travelers estimate flight ticket prices before booking. Users input journey details — departure/arrival cities, dates, preferred airline, and number of stops — and the app instantly returns a predicted fare using a trained ML model.

**Key Highlights:**
- Trained on **10,000+** real flight records from major Indian airlines
- Achieves strong predictive accuracy using **Random Forest Regression**
- Clean, production-ready Flask web app with a polished, responsive UI
- Smart UI logic prevents same-city source-destination selection

---

## 🎯 Features

| Feature | Description |
|---|---|
| **ML Prediction Engine** | Random Forest model with one-hot encoded categorical features (airline, source, destination) |
| **29 Input Features** | Includes journey day/month, departure/arrival hours, duration, airline, stops, source & destination |
| **8 City Coverage** | Bangalore, Chennai, Cochin, Delhi, Hyderabad, Kolkata, Mumbai, New Delhi |
| **12 Airlines Supported** | Jet Airways, IndiGo, Air India, SpiceJet, Vistara, GoAir, Air Asia, Trujet & more |
| **Smart Dropdowns** | Selecting a departure city auto-hides it from arrival options (and vice versa) |
| **Form Persistence** | Selected values are retained after prediction — no re-entering data |
| **Responsive Design** | Fully responsive UI built with Bootstrap 4 + custom CSS (Inter font, gradient accents) |
| **Deployment Ready** | Includes `Procfile` and `gunicorn` for Heroku/Render deployment |

---

## 🏗️ Architecture

```
User Input (Browser)
       │
       ▼
┌──────────────┐     POST /predict      ┌──────────────────┐
│  Frontend    │ ──────────────────────► │  Flask Backend   │
│  (HTML/CSS/  │                         │  (app.py)        │
│   Bootstrap) │ ◄────────────────────── │                  │
└──────────────┘   Predicted Price (₹)   │  ┌────────────┐  │
                                         │  │ RF Model    │  │
                                         │  │ (.pkl file) │  │
                                         │  └────────────┘  │
                                         └──────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Python 3.11 |
| **ML Model** | Random Forest Regressor (scikit-learn) |
| **Web Framework** | Flask 3.1 |
| **Frontend** | HTML5, CSS3, Bootstrap 4, Bootstrap Icons |
| **Data Processing** | Pandas, NumPy |
| **Model Serialization** | Pickle |
| **WSGI Server** | Gunicorn |
| **EDA & Training** | Jupyter Notebook |

---

## 📁 Project Structure

```
Flight_price/
├── app.py                  # Flask application & prediction API
├── flight_rf.pkl           # Trained Random Forest model (serialized)
├── Flight_price.ipynb      # Jupyter Notebook — EDA, feature engineering & model training
├── requirements.txt        # Python dependencies
├── Procfile                # Deployment config (Gunicorn)
├── Dataset/
│   ├── Data_Train.xlsx     # Training dataset (10,000+ records)
│   └── Test_set.xlsx       # Test dataset
├── templates/
│   └── home.html           # Main UI template (Jinja2)
├── static/
│   └── styles.css          # Custom stylesheet
└── README.md
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.10+ installed
- pip package manager

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/alokchoudhary05/Flight-Price-Prediction.git
cd Flight-Price-Prediction

# 2. Create & activate virtual environment
python -m venv myenv
# Windows
myenv\Scripts\activate
# macOS/Linux
source myenv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the application
python app.py
```

Open your browser and navigate to **http://127.0.0.1:5000**

---

## 🚀 Usage

1. **Enter Journey Details** — Select departure date/time and arrival date/time
2. **Choose Route** — Pick departure and arrival cities (smart dropdowns prevent same-city selection)
3. **Set Preferences** — Select number of stops and preferred airline
4. **Get Prediction** — Click **"Predict Price"** to see the estimated fare in ₹

---

## 🧠 Model Details

| Aspect | Detail |
|---|---|
| **Algorithm** | Random Forest Regressor |
| **Features (29)** | Total_Stops, Journey_day, Journey_month, Dep_hour, Dep_min, Arrival_hour, Arrival_min, Duration_hours, Duration_mins, + one-hot encoded Airline (11), Source (4), Destination (5) |
| **Encoding** | One-hot encoding for categorical variables (baseline categories dropped) |
| **Training Data** | 10,000+ domestic Indian flight records |
| **Serialization** | Python Pickle (.pkl) |

### Feature Engineering Pipeline
- **DateTime Parsing** → Extract day, month, hour, minute from journey/departure/arrival timestamps
- **Duration Calculation** → Compute flight duration in hours and minutes
- **Categorical Encoding** → One-hot encode airline, source, and destination with baseline category dropped

---

## 📬 Contact

**Alok Choudhary**

[![GitHub](https://img.shields.io/badge/GitHub-alokchoudhary05-181717?logo=github)](https://github.com/alokchoudhary05)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-alokk05-0A66C2?logo=linkedin)](https://www.linkedin.com/in/alokk05/)
[![Twitter](https://img.shields.io/badge/Twitter-alokk05__-1DA1F2?logo=twitter)](https://x.com/alokk05_)

---

<div align="center">

**⭐ If you found this project useful, please consider giving it a star!**

</div>
