# ☁️ Weather Prediction 🌧️

## 📌 Project Overview
This project aims to predict **`RainTomorrow`**, i.e., whether it will rain the next day in various locations across Australia based on historical daily weather observations. It leverages multiple machine learning classification models for predictive analysis using meteorological data.

---

## 📊 Dataset
- **File:** `weatherAUS.csv`
- **Source:** Australian Bureau of Meteorology
- **Target Variable:** `RainTomorrow` – indicates whether it rained the following day (`Yes` or `No`)

---

## 🔑 Key Features Used

| Feature | Description |
|--------|-------------|
| `MinTemp` | Minimum temperature (°C) |
| `MaxTemp` | Maximum temperature (°C) |
| `Rainfall` | Rainfall recorded (mm) |
| `Sunshine` | Bright sunshine hours |
| `WindGustSpeed` | Strongest wind gust speed (km/h) |
| `WindSpeed9am`, `WindSpeed3pm` | Wind speed at respective times (km/h) |
| `Humidity9am`, `Humidity3pm` | Humidity percentage |
| `Pressure9am`, `Pressure3pm` | Atmospheric pressure (hPa) |
| `Temp9am`, `Temp3pm` | Temperature (°C) |
| `Location` | Weather station location |

---

## 🧹 Preprocessing Steps

### 🔻 Column Dropping
- Dropped irrelevant columns: `Date`, `WindGustDir`, `WindDir9am`, `WindDir3pm`

### ♻️ Duplicate Handling
- Removed duplicate rows to prevent bias

### 🧩 Missing Value Imputation
- **Numerical columns**: Filled using column mean
- **Categorical columns (`RainToday`, `RainTomorrow`)**: Filled using mode

### 🔢 Categorical Encoding
- Encoded `Location`, `RainToday`, `RainTomorrow` using `LabelEncoder`

### 🔄 Data Type Conversion
- Converted all numeric features to integer (`int`) where applicable

### 📏 Outlier Detection
- Used **IQR (Interquartile Range)** method to identify outliers (currently not removed, but can be capped)

---

## ✂️ Feature Selection

### 🎯 Models Used:
- `RandomForestClassifier`
- `DecisionTreeClassifier`

### 📉 Dropped Low-importance Features:
- `RainToday`, `Cloud9am`, `Evaporation`, `Cloud3pm`

---

## 🤖 Machine Learning Models

| Model | Description |
|-------|-------------|
| **Random Forest Classifier** | Ensemble of decision trees |
| **Decision Tree Classifier** | Tree-structured model |
| **Gradient Boosting Classifier** | Boosted decision trees |
| **Gaussian Naive Bayes** | Probabilistic model using Bayes' theorem |
| **K-Nearest Neighbors** | Classifies based on nearest neighbors |
| **Logistic Regression** | Binary classification model |

> *Note: While the code mainly implements Random Forest, the imports include all the above models for potential comparison.*

---

## 🧪 Evaluation Metrics

- ✅ **Recall Score** – Identifies true positives
- 📉 **Confusion Matrix** – Displays TP, FP, FN, TN
- 🔄 **F1 Score** – Harmonic mean of precision & recall
- 🎯 **Accuracy Score** – Overall correct predictions
- 📈 **ROC AUC Score** – Binary classification effectiveness

---


