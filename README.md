# 🧳 Tourist Arrival Prediction using Search Trends and Statistical Modeling

This project predicts monthly tourist arrivals by integrating Google Trends search volumes with official tourism statistics. It combines time series forecasting techniques with machine learning models to capture both seasonal patterns and real-world demand signals derived from online behavior.

---

## 📌 Objective

To develop an accurate and interpretable forecasting model that predicts tourist arrivals based on:
- Historical arrival data
- Google search trends 
- Lag-based relationships between search activity and actual tourist visits

---

## 📂 Dataset

### 📈 Official Tourism Statistics:
- Monthly tourist arrivals (sourced from government/state tourism websites)

### 🌐 Google Trends:
- Search volume index for selected travel-related keywords
- Extracted using the `pytrends` API

---

## 🧪 Methodology

### 1. **Data Preprocessing**
- Merged Google Trends and tourism data on time index
- Handled missing values and outliers
- Scaled features using StandardScaler

### 2. **Feature Engineering**
- Performed PCA for dimensionality reduction on correlated trends
- Applied Granger Causality Test to detect lag relationships between search terms and tourist arrivals
- Created lagged features to reflect real-world decision delays (e.g., planning trips weeks in advance)

### 3. **Modeling Approaches**
Evaluated multiple forecasting models:
- SARIMA
- SARIMAX (with exogenous search features)
- LSTM
- XGBoost
- ANN
- Exponential Smoothing

### 4. **Model Selection and Tuning**
- Used grid search and time series cross-validation
- Optuna was applied to tune XGBoost hyperparameters

---

## ✅ Results

| Model         | RMSE  | MAE   |
|---------------|-------|-------|
| SARIMAX       | 3.86  | 3.10  |
| XGBoost       | 3.60  | 4.46  |
| LSTM          | ~4.00 | ~4.20 |

- SARIMAX and XGBoost with trend lags performed best
- Google Trends data improved forecast accuracy by capturing early demand signals

---

## 📊 Visualizations

- Time series plots of tourist arrivals and search trends
- Residual analysis (ADF test, Ljung-Box test)
- PCA variance explanation chart
- Predicted vs actual tourist arrivals

---

---

## 📁 Project Structure

