# Time Series Forecasting Project 📈⏳  

This project focuses on forecasting a time-series dataset with **yearly seasonality** and **daily frequency**. The dataset spans from **1/1/2013 to 1/1/2017** and includes four features: **mean temperature**, **humidity**, **wind speed**, and **mean pressure** (with pressure values in 2016 identified as outliers and excluded). The project includes data preprocessing, model evaluation with cross-validation, and predictions using multiple models, including **SARIMA**, **VAR**, **XGBoost**, **Facebook Prophet**, and **LSTM**.

---

## 📝 Problem Statement  
Forecast daily values based on the **mean temperature**, **humidity**, and **wind speed** features, while accounting for **yearly seasonality** and handling outliers in the dataset for more accurate future predictions.

---

## 🔍 Steps Followed  

### 1️⃣ Data Understanding  
- The dataset contains **1462 days** with the following features:  
  - **mean temperature (meantemp)**: In Celsius.  
  - **humidity**: Grams of water vapor per cubic meter.  
  - **wind speed**: In km/h.  
  - **mean pressure (meanpressure)**: Atmospheric pressure in atm (excluded 2016 data due to outliers).  

- The data exhibits **yearly seasonality** with nearly zero trend.  

---

### 2️⃣ Data Preprocessing  
- **Missing Values**: Handled using **forward fill**, **backward fill**, and **rolling averages**.  
- **Outlier Removal**: Excluded **mean pressure** due to outliers in 2016.  
- **Differencing**: Applied to remove seasonality and trends for better model performance.  

---

### 3️⃣ Model Building and Evaluation  

#### Baseline Models:  
- **Naive Forecasting**: Baseline model for comparison.  

#### Advanced Models:  
- **Statistical Models**:  
  - **SARIMA**: Configured with seasonal parameters (`p=d=q=1`) for yearly seasonality.  
  - **VAR**: Set with `maxlags=3` to capture lagged dependencies.  

- **Facebook Prophet**:  
  - Used **yearly seasonality** (`yearly_seasonality=True`) and **holiday data** (`holiday_df`) to account for seasonal effects and holidays.  
  - Plotted seasonal components using `plot_components()`.  

- **Machine Learning Model**:  
  - **XGBoost**: Hyperparameters fine-tuned for optimal performance.  

- **Deep Learning Model**:  
  - **LSTM**: Used with a learning rate of **0.0001** (Adam optimizer), 128 hidden units, and two dense layers (128 → 8 → 1).  

#### Cross-Validation:  
- Implemented **TimeSeriesSplit** for model validation to ensure a realistic evaluation of time-dependent models.

---

### 4️⃣ Results  

| **Model**              | **Yearly** | **Yearly** | **Daily** | **Daily**   |
|-------------------------|-------------------------|------------------------|
|                         | **MAE** | **MAPE (%)** | **MAE** | **MAPE (%)** |
| Naive Forecasting       | 2.45     | 9.33         | 1.2      | 4.7         |
| SARIMA                  | 2.16     | 8.32         | 1.209    | 4.7         |
| VAR                     | 2.16     | 8.32         | 1.209    | 4.7         |
| Facebook Prophet        | 1.57     | 5.96         | 1.16     | 4.62        |
| XGBoost                 | 1.91     | 7.25         | 0.96     | 3.7         |
| LSTM                    | NaN      | NaN          | 1.49     | 6.0         |

#### Best Model:  
- **XGBoost**: Provided the best daily forecast with **MAE = 0.96** and **MAPE = 3.7%**.  

---

### 5️⃣ Predictions and Forecasting  
- Made future predictions using **XGBoost** for daily time-series data based on the best model.  

---

### 6️⃣ Visualizations  

#### Facebook Prophet Plots:  
- Seasonal components were visualized using Prophet's `plot_components()` function.  
- Displayed yearly seasonal trends and holiday effects.

#### LSTM Model Architecture:  
- **LSTM (128 hidden units)** → **Dense (8 units)** → **Dense (1 unit)**.  
- Adam optimizer with a learning rate of **0.0001**.  

---

## 🔧 Tools and Libraries  
- **Python:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, Facebook Prophet, XGBoost, Keras.  
- **Validation:** TimeSeriesSplit for cross-validation.  
- **Optimizers:** Adam with learning rate tuning for LSTM.  

---

## 📂 File Structure  
- `data/`: Input dataset.  
- `notebooks/`: Jupyter Notebooks with code and analysis.  
- `src/`: Preprocessing, modeling, and evaluation scripts.  
- `results/`: Model outputs and performance metrics.  
- `README.md`: Project documentation (this file).  
