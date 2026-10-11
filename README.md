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

## 🎯 Project Objectives

The main objectives of OctagonIQ are to:

- Prepare and analyze historical UFC fight data.
- Engineer meaningful pre-fight features.
- Train a Machine Learning classification model.
- Evaluate predictive performance using multiple metrics.
- Track experiments and model artifacts with MLflow.
- Expose predictions through a REST API.
- Build an interactive dashboard for fighter comparison and fight prediction.

---

## 🛠️ Technologies & Tools

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Scikit-learn | Data preprocessing, model training, and evaluation |
| Random Forest Classifier | Fight outcome classification |
| MLflow | Experiment tracking and model management |
| FastAPI | REST API development |
| Uvicorn | ASGI server for the API |
| Pydantic | Request validation and data schemas |
| Streamlit | Interactive web dashboard |
| Matplotlib | Data visualization |
| Git | Version control |
| GitHub | Source code hosting |

---

## 🔬 Machine Learning Workflow

The project follows a structured Machine Learning pipeline.

### 1. Data Collection and Exploration

- Work with historical UFC fight datasets.
- Inspect dataset structure, feature types, and missing values.
- Examine fighter attributes and fight-related information.
- Identify unsuitable fields and potential sources of data leakage.

### 2. Data Cleaning and Preparation

- Handle missing values.
- Prepare the dataset for Machine Learning.
- Exclude post-fight statistics from the prediction features.
- Exclude unavailable betting odds and unsuitable identifiers.
- Prepare the target variable for binary classification.

### 3. Feature Engineering

- Prepare fighter physical attributes.
- Engineer historical fighter statistics.
- Organize fighter information into a consistent feature structure.
- Use chronological information when constructing historical features.

### 4. Data Preprocessing

The Scikit-learn preprocessing pipeline includes:

- Median imputation for numerical features.
- Most-frequent imputation for categorical features.
- Standard scaling for numerical features.
- One-hot encoding for categorical features.

### 5. Model Training

A Random Forest Classifier was trained using the following configuration:

| Parameter | Value |
|---|---:|
| Number of estimators | 300 |
| Maximum depth | 12 |
| Minimum samples per leaf | 3 |
| Random state | 42 |

The dataset was divided chronologically into training, validation, and test sets.

| Dataset | Samples |
|---|---:|
| Training | 6,138 |
| Validation | 1,315 |
| Test | 1,316 |

### 6. Model Evaluation

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Brier score
- Log loss

### 7. Experiment Tracking with MLflow

MLflow was used to track model experiments and save model artifacts.

The project uses local MLflow tracking with SQLite.

### 8. REST API Development

FastAPI exposes the prediction model through an HTTP endpoint.

The API includes:

- A health endpoint.
- A prediction endpoint.
- Input validation using Pydantic.
- Fighter win probabilities in the prediction response.

### 9. Interactive Dashboard

The Streamlit dashboard provides:

- Fighter selection.
- Fighter profile visualization.
- Physical attribute comparison.
- Historical record display.
- A Tale of the Tape comparison table.
- Predicted winner visualization.
- Win probability comparison.

---

## 📊 Model Performance

The following results were obtained from the current experimental pipeline.

| Metric | Validation | Test |
|---|---:|---:|
| Accuracy | 96.20% | 95.59% |
| Precision | 97.70% | 96.24% |
| Recall | 94.30% | 94.39% |
| F1-score | 95.97% | 95.31% |
| ROC-AUC | 99.49% | 99.14% |

### Additional Test Metrics

| Metric | Test Result |
|---|---:|
| Brier Score | 0.0786 |
| Log Loss | 0.2990 |

> **Important:** These are experimental results, not a guarantee of real-world performance. The target construction, dataset structure, potential data leakage, chronological generalization, and probability calibration require further investigation before these metrics can be interpreted as reliable real-world fight predictions.

---

## 📁 Project Structure

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
├── screenshots/
│   ├── Screenshot 2026-10-11 180836.png
│   ├── Screenshot 2026-10-11 180853.png
│   └── Screenshot 2026-10-11 180911.png
│
├── data/
│   └── raw/
│
├── UFC_Fight_Prediction.py
├── feature_importance_random_forest.csv
├── mlflow_dataset_info.json
├── mlflow_model_features.txt
├── permutation_importance_validation.csv
├── requirements.txt
├── Dockerfile
├── .dockerignore
├── .gitignore
└── README.md
