
##  Weather Trend Forecasting

This project analyzes the Global Weather Repository dataset to forecast future temperature trends using time-series and machine learning models. It addresses both basic and advanced tasks outlined in the PM Accelerator Tech Assessment.

---

##  Dataset

- **Source**: https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository/code  (World Weather Repository)
- **Content**: Daily weather records with over 40 features from cities worldwide
- **Used Features**: Temperature, humidity, wind speed, visibility, air quality, and more
- **Focused Variable**: `temperature_celsius`

---

## Data Cleaning & Preprocessing

- Converted `last_updated` to datetime format and set it as the index
- Resampled the dataset to daily frequency using mean
- Filled missing numeric values using median imputation
- Removed outliers using the IQR method
- Normalized numerical features with `StandardScaler`
- Handled missing values using median imputation


---

## Exploratory Data Analysis (EDA)

- Visualized temperature and precipitation trends over time
- Plotted boxplots to detect outliers and seasonal variance
- Generated correlation heatmaps  to uncover relationships between features and for feature selection
- Histogram and distribution analysis for key variables
- Boxplots and time plots helped identify seasonal trends

---

#### Model Building
- Built individual forecasting models using:
  - **ARIMA** (univariate time series)
  - **Prophet** (seasonality and trend modeling)
  - **XGBoost** (multivariate regression)
- Evaluated using MAE and RMSE
- Used `last_updated` for time-aware splits


##  Advanced EDA & Anomaly Detection

- Applied Z-score-based anomaly detection (threshold = 3)
- Identified and plotted temperature anomalies across time

---

##  Forecasting Models

Three models were implemented and evaluated:

| Model     | Type                  | Approach                      |
|-----------|-----------------------|-------------------------------|
| ARIMA     | Statistical (Univariate) | Captures time-based trend |
| Prophet   | Additive Time Series   | Seasonality + trend modeling |
| XGBoost   | Machine Learning        | Regression with lag/rolling features |

Each model was trained on 80% of the time series and tested on the remaining 20%.

---

## Ensemble Forecasting

- Created a simple average ensemble combining ARIMA, Prophet, and XGBoost
- Aligned all model outputs to a common date index
- Handled NaNs using `skipna=True` for robustness

---

## Evaluation Metrics

| Model     | MAE     | RMSE    |
|-----------|---------|---------|
| ARIMA     | 0.1345  | 0.1656  |
| Prophet   | 0.1408  | 0.1757  |
| XGBoost   | 0.0912  | 0.1121  |
| Ensemble  | 0.0862  | 0.1048

---

## Unique Analyses

- **Climate Trend Analysis**: Year-wise mean temperature visualization
- **Environmental Correlation**: PM2.5, CO, visibility vs. temperature trends
- **Feature Importance**:
  - Mutual Information
  - Recursive Feature Elimination (RFE)
  - XGBoost built-in importance plot

---

##  Spatial Analysis

- Plotted average temperature by country
- Visualized temperature distributions across multiple regions

---

## Key Insights

- XGBoost was the most accurate individual model, leverages multivariate relationships but may underfit on extremes
- Ensemble forecasting produced the most stable, accurate and generalizable results
- ARIMA was limited in adapting to short-term fluctuations
- Visibility and air quality features were strong predictors of temperature in many cities
- Prophet effectively captures trend and seasonality.

---

## Deliverables

- All analyses, models, and visualizations are contained within a single Jupyter notebook
- This README provides a full walkthrough of the methodology and results

---

## Environment

- Python 3.8+
- Libraries used:
  - pandas, numpy, matplotlib, seaborn
  - scikit-learn, xgboost, statsmodels
  - prophet, plotly

---

## Author

**Sudhira Chegu**  
Graduate Student – Computer Science  
University of Florida


---






