<div align="center">

# 🥊 OctagonIQ
### UFC Fight Prediction with Machine Learning

A machine learning application for UFC fight outcome prediction, fighter comparison, and probability visualization.

**Python · Scikit-learn · FastAPI · Streamlit · MLflow**

</div>

---

## 📸 Application Preview

OctagonIQ provides an interactive dashboard to compare fighters, explore their profiles, and visualize model predictions.

### 1. Fighter Profiles

Explore fighter profiles, physical attributes, and historical records.

![Fighter Profiles](app%20screenshots/fighter-profiles.png)

### 2. Tale of the Tape

Compare fighter attributes side by side, including height, weight, reach, and historical records.

![Tale of the Tape](app%20screenshots/tale-of-the-tape.png)

### 3. Prediction Results

View the predicted winner and compare the model-estimated win probabilities for both fighters.

![Prediction Result](app%20screenshots/prediction-result.png)

---

## 🎯 Project Overview

**OctagonIQ** is a Machine Learning project developed to predict UFC fight outcomes using historical fight data and pre-fight fighter characteristics.

The project combines data preparation, feature engineering, model training, evaluation, experiment tracking, API development, and interactive visualization.

The objective is to demonstrate an end-to-end Machine Learning workflow through a practical sports analytics application.

> **Disclaimer:** Predictions are model-generated estimates and do not guarantee actual fight outcomes.

---

## ✨ Key Features

- 🥊 UFC fight outcome prediction.
- 👤 Fighter selection and profile visualization.
- 📊 Side-by-side fighter comparison.
- 📏 Physical attribute comparison.
- 🧮 Historical record exploration.
- 📈 Win probability visualization.
- ⚡ REST API for predictions.
- 🧪 MLflow experiment tracking.
- 🔍 Feature importance analysis.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and preprocessing |
| NumPy | Numerical operations |
| Scikit-learn | Machine Learning and preprocessing pipelines |
| Random Forest | Fight outcome classification |
| MLflow | Experiment tracking and model artifact management |
| FastAPI | REST API development |
| Uvicorn | ASGI server |
| Streamlit | Interactive web dashboard |
| Pydantic | API request validation |
| Git | Version control |
| GitHub | Source code hosting |

---

## 🔄 Project Workflow

### 1. Data Preparation

Historical UFC fight data was used as the basis for the prediction pipeline.

The preparation workflow included:
- Inspecting the dataset and its structure.
- Identifying relevant fighter and fight attributes.
- Removing unsuitable or unavailable features.
- Preparing the target variable.
- Organizing data for chronological evaluation.

### 2. Feature Engineering

Features were prepared to represent information available before a fight.

Examples include:
- Previous wins, losses, and draws.
- Fighter height and weight.
- Reach.
- Fighting stance.
- Weight class.
- Fight format and other pre-fight attributes.

Post-fight statistics and information that could reveal the fight outcome were excluded from the intended prediction feature set.

### 3. Data Preprocessing

The Scikit-learn preprocessing pipeline included:
- Median imputation for numerical features.
- Most-frequent imputation for categorical features.
- Standard scaling for numerical inputs.
- One-hot encoding for categorical variables.

### 4. Model Training

A Random Forest classifier was trained to predict the fight outcome.

The model was evaluated using chronological training, validation, and test splits.

### 5. Model Evaluation

The model was evaluated using:
- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Brier score
- Log loss

Feature importance analysis was also performed to help interpret model behavior.

### 6. Experiment Tracking

MLflow was used to record model experiments and manage logged model artifacts.

### 7. API Development

FastAPI provides endpoints for health checks and fight predictions.

Pydantic validates incoming prediction requests, while Uvicorn runs the API server.

### 8. Dashboard Development

Streamlit provides an interactive interface to:
- Select fighters.
- Explore fighter profiles.
- Compare physical attributes.
- Inspect historical records.
- Visualize prediction results and estimated probabilities.

---

## 🧠 Machine Learning Model

The current model is a **Random Forest Classifier**.

### Model Configuration

| Parameter | Value |
|---|---:|
| Algorithm | Random Forest Classifier |
| Number of estimators | 300 |
| Maximum depth | 12 |
| Minimum samples per leaf | 3 |
| Random state | 42 |

The model uses numerical and categorical preprocessing before classification.

---

## 📊 Evaluation Results

The current recorded evaluation metrics are:

| Metric | Validation | Test |
|---|---:|---:|
| Accuracy | 96.20% | 95.59% |
| Precision | 97.70% | 96.24% |
| Recall | 94.30% | 94.39% |
| F1-score | 95.97% | 95.31% |
| ROC-AUC | 99.49% | 99.14% |

Additional test metrics:

| Metric | Test |
|---|---:|
| Brier score | 0.0786 |
| Log loss | 0.2990 |

**Evaluation note:** These results reflect the current dataset and evaluation pipeline. The unusually high scores require further investigation into target construction, potential data leakage, chronological generalization, and probability calibration before drawing conclusions about real-world predictive performance.

---

## 🏗️ Project Structure

```text
octagoniq-ufc-prediction/
│
├── app/
│   ├── __init__.py
│   └── main.py
│
├── dashboard/
│   └── streamlit_app.py
│
├── app screenshots/
│   ├── fighter-profiles.png
│   ├── tale-of-the-tape.png
│   └── prediction-result.png
│
├── UFC_Fight_Prediction.py
├── feature_importance_random_forest.csv
├── permutation_importance_validation.csv
├── mlflow_dataset_info.json
├── mlflow_model_features.txt
├── .gitignore
└── README.md
