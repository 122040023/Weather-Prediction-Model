# Weather-Prediction-
**(Academic Coursework Project)**

## 📘 Project Type
**University Academic Coursework**  
This project was completed as part of a university machine learning / data science course and is intended **strictly for educational and academic purposes**.

---

## 📌 Project Overview

This project implements an **end-to-end Logistic Regression pipeline** in Python to predict **whether it will rain tomorrow in Australia**, using historical weather data.

The implementation demonstrates best practices in **data preprocessing, feature engineering, model training, evaluation, and optimization** using Scikit-Learn.

- **Problem Type:** Binary Classification  
- **Target Variable:** `RainTomorrow` (Yes / No)  
- **Model Used:** Logistic Regression  
- **Dataset:** Australian Weather Dataset (`weatherAUS.csv`)  
- **Final Test Accuracy:** ~85%

---

## 🧠 Learning Objectives

This coursework was designed to demonstrate understanding of:

- Logistic Regression theory and intuition
- Exploratory Data Analysis (EDA)
- Handling missing values
- Feature engineering and encoding
- Model training and evaluation
- Bias–variance trade-off
- Threshold tuning
- Cross-validation and feature selection
- Hyperparameter optimization

---


---

## 📊 Dataset Description

The dataset contains **142,193 observations** and **24 variables**, including daily weather measurements collected from multiple Australian weather stations.

### Target Variable
- `RainTomorrow`  
  - **Yes** → Rain occurs the next day  
  - **No** → No rain the next day  

### Feature Types

**Numerical Variables**
- Temperature, rainfall, evaporation
- Wind speed
- Humidity, pressure
- Cloud cover

**Categorical Variables**
- Location
- Wind direction
- RainToday (Yes / No)

> ⚠️ The feature `RISK_MM` was removed to avoid data leakage.

---

## 🔧 Data Preprocessing & Feature Engineering

### 1. Missing Value Handling
- **Numerical features:** Median imputation (robust to outliers)
- **Categorical features:** Mode imputation

### 2. Date Feature Engineering
- Extracted:
  - `Year`
  - `Month`
  - `Day`
- Dropped the original `Date` column

### 3. Outlier Treatment
Outliers were capped using a **top-coding (IQR-based)** approach for:
- `Rainfall`
- `Evaporation`
- `WindSpeed9am`
- `WindSpeed3pm`

### 4. Categorical Encoding
- `RainToday`: Binary Encoding
- Other categorical variables: One-Hot Encoding

### 5. Feature Scaling
- Min-Max Scaling applied to all features before model training

---

## 🤖 Model Training

The Logistic Regression model was trained using Scikit-Learn:

```python
from sklearn.linear_model import LogisticRegression

logreg = LogisticRegression(
    solver='liblinear',
    random_state=0
)
logreg.fit(X_train, y_train)


## 📂 Project Structure

