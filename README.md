# 🥊 OctagonIQ — UFC Fight Prediction

A Machine Learning application for UFC fight outcome prediction, built with Python, Scikit-learn, FastAPI, and Streamlit.

## 📸 Application Preview

### Fighter Profiles
Explore fighter profiles, physical attributes, and historical records.

<img src="screenshots/Screenshot%202026-10-11%20180836.png" alt="Prediction Result" width="100%">

### Tale of the Tape
Compare fighter statistics side by side.

<img src="screenshots/Screenshot%202026-10-11%20180853.png" alt="Tale of the Tape" width="100%">

### Prediction Results
Visualize the predicted winner and model-estimated win probabilities.

<img src="screenshots/Screenshot%202026-10-11%20180911.png" alt="Fighter Profiles" width="100%">

## 🎯 Project Overview

OctagonIQ uses historical UFC data and pre-fight fighter characteristics to estimate fight outcomes.

The project covers data preparation, feature engineering, model training, evaluation, experiment tracking, API development, and dashboard visualization.

## 🛠️ Technologies

- **Python** — Core programming language
- **Pandas & NumPy** — Data processing
- **Scikit-learn** — Preprocessing and Machine Learning
- **Random Forest** — Fight outcome classifier
- **MLflow** — Experiment tracking and model artifacts
- **FastAPI** — Prediction REST API
- **Uvicorn** — API server
- **Streamlit** — Interactive dashboard
- **Pydantic** — Input validation
- **Git & GitHub** — Version control

## ⚙️ Project Workflow

1. **Data Preparation:** Inspect and clean historical UFC data.
2. **Feature Engineering:** Prepare fighter statistics and pre-fight attributes.
3. **Preprocessing:** Impute missing values and encode categorical features.
4. **Model Training:** Train a Random Forest classifier.
5. **Evaluation:** Measure Accuracy, Precision, Recall, F1-score, and ROC-AUC.
6. **Experiment Tracking:** Log experiments and model artifacts with MLflow.
7. **API Development:** Expose predictions through FastAPI.
8. **Dashboard Development:** Visualize fighter profiles and prediction probabilities with Streamlit.

## 📊 Model Evaluation

| Metric | Validation | Test |
|---|---:|---:|
| Accuracy | 96.20% | 95.59% |
| Precision | 97.70% | 96.24% |
| Recall | 94.30% | 94.39% |
| F1-score | 95.97% | 95.31% |
| ROC-AUC | 99.49% | 99.14% |

> **Note:** These are experimental results from the current pipeline. Further investigation of possible data leakage, target construction, chronological generalization, and probability calibration is needed before interpreting them as real-world predictive performance.

## 🚀 Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/Aymanel7r/octagoniq-ufc-prediction.git
cd octagoniq-ufc-prediction
