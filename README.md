# Time Series Forecasting Project 📈⏳  

This project focuses on forecasting time-series data using a comprehensive pipeline, including data visualization, preprocessing, and modeling with statistical, machine learning, and deep learning techniques. The goal is to predict future trends while comparing models to find the most accurate one for the dataset.  

---

## 📝 Problem Statement  
Build an end-to-end time series forecasting pipeline to understand trends, handle challenges like seasonality and missing values, and predict future values using baseline models and advanced forecasting techniques.  

---

## 🔍 Steps Followed  

### 1️⃣ Understanding the Dataset  
- Explored the data to identify patterns, trends, seasonality, and anomalies.  

---

### 2️⃣ Visualization  
- Plotted time-series data to detect seasonality and trends.  
- Applied differencing to remove seasonality and trends for better model performance.  

---

### 3️⃣ Preprocessing  
- Handled missing values using **forward fill (ffill)**, **backward fill (bfill)**, and **rolling averages**.  
- Detected and removed outliers to ensure clean and reliable input for modeling.  

---

### 4️⃣ Modeling  

#### Baseline Models:  
- **Naive Forecasting**: Used as the baseline to compare advanced models.  
- **Statistical Models**: SARIMA and VAR provided additional baseline benchmarks.  

#### Advanced Models:  
- **Facebook Prophet**: Effective for handling seasonality and holiday effects.  
- **Machine Learning Models**: XGBoost for leveraging lag features and advanced forecasting.  
- **Deep Learning Models**: LSTM to predict sequential patterns, though less effective due to a small dataset.  

#### Model Insights:  
- Used baseline models to evaluate performance and provide a comparison standard.  
- Gained understanding of time-based splitting and lag features.  
- Evaluated and addressed underfitting and overfitting for optimal predictions.  
- Predicted future values with the best-performing model (Prophet and XGBoost).  

---

### 5️⃣ Results  

| **Model**              | **Yearly**              | **Daily**              |
|-------------------------|-------------------------|------------------------|
|                         | **MAE** | **MAPE (%)** | **MAE** | **MAPE (%)** |
| Naive Forecasting       | 2.45     | 9.33         | 1.2      | 4.7         |
| SARIMA, VAR             | 2.16     | 8.32         | 1.209    | 4.7         |
| Facebook Prophet        | 1.57     | 5.96         | 1.16     | 4.62        |
| XGBoost                 | 1.91     | 7.25         | 0.96     | 3.7         |
| LSTM                    | NaN      | NaN          | 1.49     | 6.0         |

---

## 🔧 Tools and Libraries  
- **Python:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn.  
- **Models:** SARIMA, VAR, Facebook Prophet, XGBoost, LSTM.  
- **Validation Metrics:** MAE, MAPE.  

---

## 📂 File Structure  
- `data/`: Input dataset.  
- `notebooks/`: Jupyter Notebooks with code and analysis.  
- `src/`: Preprocessing, modeling, and evaluation scripts.  
- `results/`: Model outputs and performance metrics.  
- `README.md`: Project documentation (this file).  
