# 🌾 Smart Aero Field
### Translating NASA Earth Data into Hyper-Local Farm Decisions

**Smart Aero Field** is an AI-powered agricultural decision-support platform developed by **Team Scarlet** for the **NASA Space Apps Challenge 2026**.

The platform transforms NASA Earth observation and climate data into practical, localized, and Bangla-friendly agricultural insights for farmers in Bangladesh. By combining satellite-derived environmental information, machine learning, and generative AI, Smart Aero Field aims to bridge the gap between complex Earth science data and real-world farming decisions.

**Challenge: Field Shift: Adapting Farms with NASA Data ** 

---

## 🚀 Live Project

| Resource | Link |
|---|---|
| 🌐 Live Application | [Smart Aero Field](https://smart-aero-field.vercel.app/) |
| 📚 ML API Documentation | [Interactive Swagger API](https://agriii-tns8.onrender.com/docs) |




---

## 🎯 The Problem

Agriculture in Bangladesh is highly dependent on rainfall, temperature, seasonal patterns, and local environmental conditions.

However, changing climate patterns are making traditional agricultural calendars less reliable. Farmers often continue to follow historical planting schedules without having access to understandable, location-specific climate evidence.

Although NASA provides extensive Earth observation and climate datasets, this information is often too technical to translate directly into everyday farming decisions.

**The challenge is not the lack of environmental data. It is making that data useful at the farm level.**

## 💡 Our Solution

Smart Aero Field converts environmental and agricultural data into accessible, localized decision-support information.

Our platform integrates:

- NASA Earth observation and climate datasets.
- Historical rainfall and temperature analysis.
- Climate-adjusted planting-window recommendations.
- Machine-learning-based crop suitability and risk predictions.
- AI-assisted crop disease analysis.
- A Bangla-friendly AI agricultural assistant.

Our primary innovation is the **Planting-Window & Climate Advisory**, which demonstrates how historical climate patterns can help inform better planting decisions.

---

## 🛰️ Killer Demo: Planting-Window & Climate Advisory

<text>Turning 25 years of climate evidence into one practical farming decision.</text>

The Planting-Window feature analyzes historical climate information from **2001–2026** to investigate how rainfall availability and temperature-related growing conditions have shifted over time.

It focuses on two agricultural indicators:

### 1. Usable Rainfall Onset

Identifies when cumulative rainfall reaches a **50 mm soil-recharge threshold**, providing an indicator of when sufficient rainfall may become available for planting-related activities.

### 2. Growing Degree Days (GDD)

Tracks cumulative Growing Degree Days using a **10°C base temperature** to understand temperature-related crop development conditions.

### How the demonstration works

1. The user selects a Bangladeshi district and crop.
2. The system analyzes historical climate indicators.
3. It compares earlier and more recent climate distributions.
4. It calculates the observed shift in usable-rain onset and evaluates growing conditions.
5. It presents a climate-adjusted planting-window recommendation.
6. The final result is communicated through an actionable decision sentence in Bangla.

### Example: Rajshahi – Aman Rice

In our demonstration, the usable-rain onset indicator shows an approximately **11-day delay compared with 2001**.

The application uses this historical comparison to demonstrate how planting schedules can be reconsidered based on changing climate conditions.

The objective is simple:

**Farmers should not need to understand satellite data or statistical charts to benefit from Earth science. They need a clear and understandable farming decision.**

---

## ✨ Key Features

### 🌦️ 1. Planting-Window & Climate Advisory

- Historical climate analysis from 2001–2026.
- Rainfall-onset and GDD indicators.
- Climate-adjusted planting-window demonstration.
- District and crop-oriented analysis.
- Bangla-friendly actionable recommendations.

### 🛰️ 2. NASA Earth Data Integration

Integrates environmental information from NASA Earth science data services.

**Data sources include:**

- [NASA POWER](https://power.larc.nasa.gov/)
- [NASA GPM IMERG](https://gpm.nasa.gov/data/imerg)
- [NASA MODIS](https://modis.gsfc.nasa.gov/data/)

Relevant climate variables include precipitation, temperature, relative humidity, and solar radiation, depending on the specific workflow.

### 🌾 3. Crop Suitability Prediction

A trained machine-learning model estimates crop suitability using available environmental and agricultural features.

### ⚠️ 4. Crop Risk Prediction

A separate machine-learning model provides crop-risk predictions through the cloud-hosted Python API.

### 🍃 5. Dual AI Leaf Disease Scanner

- Computer-vision-based leaf image classification.
- AI-assisted cross-validation using Google Gemini 2.5 Flash.
- Possible disease identification.
- Organic and chemical treatment suggestions.

The results are preliminary AI-assisted assessments, not confirmed disease diagnoses.

### 🤖 6. Bangla AI Agronomist

A Gemini-powered agricultural assistant designed to support farmers with:

- Crop management guidance.
- Fertilizer scheduling (Urea, TSP, MoP, Zinc).
- Irrigation and water management.
- Crop-health questions.
- Weather-related farming decisions.
- General agricultural recommendations.

### 📊 7. Farmer Dashboard

A centralized interface providing access to available:

- Weather and environmental information.
- Crop recommendations.
- Crop-risk predictions.
- Disease analysis.
- AI agricultural assistance.

Supports Bangla and English interfaces.

---

## 🔄 System Architecture

```text
       NASA EARTH OBSERVATION DATA
       POWER · GPM IMERG · MODIS
                    |
                    v
          DATA RETRIEVAL & PROCESSING
             District-based Analysis
                    |
                    v
          DATA & FEATURE ENGINEERING
                    |
          +---------+---------+
          |                   |
          v                   v
     ML PREDICTION       CLIMATE ANALYSIS
     Crop Risk           Rainfall Onset
     Crop Suitability    Growing Degree Days
          |                   |
          +---------+---------+
                    |
                    v
             AI-ASSISTED SERVICES
             Disease Analysis
             Bangla Agronomist
                    |
                    v
             SMART AERO FIELD
              Web Application
                    |
                    v
             BANGLADESH FARMERS
          Localized Farming Guidance
```

---

## ☁️ API & Machine-Learning Service

Smart Aero Field includes a Python-based machine-learning service that loads trained crop-risk and crop-suitability models and exposes prediction functionality through a REST API.

**Interactive API Documentation:**

https://agriii-tns8.onrender.com/docs

### Example API Request

The prediction endpoint accepts a district and a date in `YYYYMMDD` format.

```json
{
  "district": "Dhaka",
  "date": "20260601"
}
```

The API processes the supplied information and returns predictions according to the deployed model pipeline.

Refer to the Swagger documentation for available endpoints and their current response structures.

### Machine-Learning Workflow

```text
Raw Data
   |
   v
Data Preparation
   |
   v
Feature Processing
   |
   v
Model Training
   |
   v
Serialized Model Files
   |
   v
Prediction API
   |
   v
Application Integration
```

**Model files:**
- `crop_risk_model.pkl`
- `crop_suitability_model.pkl`

---

## 🏗️ Project Structure

```text
smartaerofield/
│
├── Agri AI-ML/
│   ├── data/
│   ├── AgriNav.ipynb
│   ├── main.py
│   ├── predict.py
│   ├── train_model.py
│   ├── crop_risk_model.pkl
│   ├── crop_suitability_model.pkl
│   └── requirements.txt
│
├── Smart-Aero-Field-main/
│   ├── api/
│   │   ├── ai/
│   │   ├── gemini/
│   │   ├── nasa/
│   │   └── predict.ts
│   │
│   ├── public/
│   ├── src/
│   ├── .env.example
│   ├── firestore.rules
│   ├── package.json
│   ├── server.ts
│   ├── vercel.json
│   └── vite.config.ts
│
├── LICENSE
└── README.md
```

---

## 🧰 Technology Stack

| Category | Technologies |
|---|---|
| Frontend | React, TypeScript, Vite, Tailwind CSS |
| Application / API | Node.js, TypeScript, Express, REST APIs |
| Machine Learning | Python, scikit-learn, Pandas, NumPy |
| Data Analysis | Jupyter Notebook |
| Generative AI | Google Gemini 2.5 Flash |
| Earth Observation | NASA POWER, GPM IMERG, MODIS |
| Backend Services | Firebase |
| Deployment | Vercel, Render |

---

## 💻 Run Locally

### Prerequisites

- Node.js and npm
- Python 3
- pip

### 1. Clone the Repository

```bash
git clone https://github.com/saif76r/smartaerofield.git
cd smartaerofield
```

### 2. Run the Web Application

```bash
cd Smart-Aero-Field-main
npm install
npm run dev
```

The development server will display the local application URL in the terminal.

### 3. Run the Machine-Learning API

Open a separate terminal from the repository root.

```bash
cd "Agri AI-ML"
python -m venv venv
```

Activate the virtual environment.

**Windows:**

```bash
venv\Scripts\activate
```

**Linux / macOS:**

```bash
source venv/bin/activate
```

Install dependencies and start the API:

```bash
pip install -r requirements.txt
python main.py
```

The API will start using the host and port configured in the application.

---

## 🔐 Environment Configuration

Some application features require API keys and service configuration.

1. Navigate to `Smart-Aero-Field-main/`.
2. Create a `.env` file using `.env.example` as a reference.
3. Add the required environment variables.
4. Never commit private credentials.

Example:

```env
GEMINI_API_KEY=your_gemini_api_key
FIREBASE_API_KEY=your_firebase_api_key
API_URL=your_api_url
```

Use the exact variable names required by the source code.

---



## 🔭 Future Improvements

- Higher-resolution Earth observation and climate datasets.
- More crop-specific historical agricultural datasets.
- Independent validation against observed agricultural records.
- Improved climate-adjusted recommendations.
- Additional crop types and disease categories.
- Offline and low-connectivity functionality.
- Dedicated mobile application.
- Expanded localized Bangla agricultural assistance.

---

## 👥 Team Scarlet

**NASA Space Apps Challenge 2026**

**Project:** Smart Aero Field

| Role | Responsibility |
|---|---|
| Team Leader & Developer | Project coordination, software development and system integration |
| UI/UX Designer | User interface and user experience design |
| AI/ML Engineer | Machine-learning models and AI pipeline |
| Research & Presenter | Research, documentation and presentation |
| Testing & Ideation | Testing, validation and project ideation |

---

## 📜 License

This project is licensed under the **Apache License, Version 2.0**. See the [LICENSE](LICENSE) file for details.

Copyright © 2026 Team Scarlet.

---

<p align="center">
  <strong>🌾 Smart Aero Field</strong><br/>
  <em>From Earth Data to Farm Decisions.</em><br/><br/>
  Built with innovation for a climate-resilient agricultural future.
</p>
