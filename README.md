# Forecasting-Air-Passengers
Prediction of air passenger numbers using SARIMA and XGBOOST
Air Passenger Forecasting 

## Project Overview

This project analyzes and forecasts monthly air passenger numbers using two approaches: a statistical time-series model (SARIMA) and a machine-learning model (XGBoost).
The main objective is to understand the trend and seasonality patterns of air travel demand and produce reliable short- and medium-term forecasts that support strategic decision-making for the aviation sector.

## Data Source

The analysis uses the classic AirPassengers dataset — a benchmark time-series dataset representing monthly totals of international airline passengers.It is available to download on the following link: <a href='https://www.kaggle.com/datasets/ashfakyeafi/air-passenger-data-for-time-series-analysis'>Dataset</a>
Frequency: Monthly
Date Range: 1949 – 1960
Observations: 144


## Tools

Python (Jupyter Notebook) — main environment for analysis
Pandas, NumPy — for data manipulation and preprocessing
Matplotlib, Seaborn — for visualizations and time series plots
Statsmodels — for SARIMA model building and diagnostics
Scikit-learn — for preprocessing and evaluation
XGBoost — for gradient boosting regression modeling

## Data Cleaning and Preparation

The data preparation phase included the following steps:
Data Loading and Inspection — The AirPassengers dataset was imported and reviewed for structure and completeness.
Datetime Conversion — The “Month” column was converted to a proper DatetimeIndex for time series operations.
Missing Values Check — Confirmed no missing data in the series.
Decomposition — The series was decomposed into trend, seasonal, and residual components to explore underlying patterns.
Stationarity Test — An Augmented Dickey-Fuller (ADF) test was applied to determine differencing needs for the SARIMA model.
Feature Engineering for XGBoost — Lag and time-based features (month, year, etc.) were created to enable supervised learning.
Train-Test Split — The dataset was split into 80% training and 20% testing for performance evaluation.

## Exploratory Data Analysis

Exploratory analysis was conducted to understand the structure and behavior of the time series:
Trend Identification: Revealed a strong upward trend in passenger numbers over time.
Seasonality Detection: Each year showed repeating peaks and troughs, confirming monthly seasonality.
Stationarity Check: Non-stationary at the original level but became stationary after first differencing.
Autocorrelation (ACF) and Partial Autocorrelation (PACF): Used to guide parameter selection for SARIMA.

## Modeling Approaches
1. SARIMA Model

The Seasonal ARIMA model captures both trend and seasonality.
Model parameters (p, d, q) × (P, D, Q, s) were chosen based on ACF/PACF plots and diagnostic checks.
The model was fitted, residuals were analyzed to ensure white noise behavior, and forecasts were generated for the test period.

2. XGBoost Model

A machine learning regression model was trained using lag features as predictors.
GridSearchCV was used to find optimal hyperparameters (learning rate, max depth, estimators).
The model predicted future passenger numbers using prior time-lagged values.
Predictions were compared against the actual test data for evaluation.
Model Evaluation (MAPE)
Both models were evaluated using the Mean Absolute Percentage Error (MAPE) metric on the test set.

Model	MAPE (%)
SARIMA	4.66
XGBoost	12.96

## Model Evaluation (MAPE)

Both models were evaluated using the Mean Absolute Percentage Error (MAPE) metric on the test set.

Model	MAPE (%)
SARIMA	4.66
XGBoost	12.96

## Conclusion:
The SARIMA model outperformed XGBoost, achieving a lower MAPE (4.66%) compared to XGBoost (12.96%).
This indicates that the SARIMA model, which directly models the trend and seasonal structure, was better suited for this dataset’s strong periodic patterns.

## Results / Findings

The time series demonstrates a clear upward trend and strong monthly seasonality.
The SARIMA model provided superior accuracy and reliability for forecasting compared to XGBoost.
XGBoost captured general patterns but struggled to model consistent seasonality.
Model diagnostics confirmed that SARIMA residuals followed random noise, validating the fit.
Future forecasts suggest continuous growth in air passenger numbers year over year.

