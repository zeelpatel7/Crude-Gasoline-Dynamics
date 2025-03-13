# Crude Gasoline Dynamics: Cointegration Forecasting for Energy Arbitrage

## Project Overview

This project is the final assignment for a Time Series Analysis and Forecasting course. The main objective is to model and forecast monthly gasoline prices (and the gasoline–crude oil spread) using four different time-series forecasting approaches:

1. ECM (Error Correction Model)
2. VECM (Vector Error Correction Model)
3. ARIMAX (AutoRegressive Integrated Moving Average with eXogenous variables)
4. LSTM (Long Short-Term Memory neural network)
   
We have monthly crude oil and gasoline price data spanning 1993 to 2024, along with some exogenous variables related to both crude oil and gasoline. We use 1993–2023 as training data and 2024 as testing data.


## Cointegration & Spread Trading

1. We first check if gasoline and crude oil are cointegrated using the Engle-Granger test, and confirm that they are.
2. Each model forecasts future gasoline prices.
3. We also forecast the spread between gasoline and crude oil (or at least derive it from forecasted gasoline minus actual crude).
4. We convert these forecasted spreads into trading signals (Buy, Sell, or Hold) using a z-score threshold (e.g., ±1.5 standard deviations from the historical mean).
   
Then we evaluate the profitability of the trading signals over the 2024 out-of-sample period.


## Project Structure

├── data/
│   └── data.xlsx            # Example raw data (not always stored in repo)
├── notebooks/
│   ├── ECM_Model.ipynb      # ECM modeling & forecasting
│   ├── VECM_Model.ipynb     # VECM modeling & forecasting
│   ├── ARIMAX_Model.ipynb   # ARIMAX modeling & forecasting
│   └── LSTM_Model.ipynb     # LSTM modeling & forecasting
├── src/
│   └── helper_functions.py  # utility functions (preprocessing, etc.)
├── README.md                # Project description (this file)
└── requirements.txt         # Python dependencies


## Data

- Crude Oil Prices: Monthly data (1993–2024) in $/barrel.
- Gasoline Prices: Monthly data (1993–2024) in $/gallon.
- Exogenous Variables: Additional monthly data such as interest rates, production levels, or macro indicators related to oil/gasoline (optional).


## Dependencies & Installation

1. R Environment
The ECM, VECM, and ARIMAX models are written in R and typically run in RStudio. Make sure you have:

 - R (version ≥ 4.0 recommended)
 - RStudio (optional, but strongly recommended)

Within R, you’ll likely need several packages:

 - tidyverse (for data wrangling and visualization)
 - readxl (for reading Excel files)
 - tseries (for ADF tests)
 - lmtest (for diagnostic tests)
 - forecast (for ARIMA, ARIMAX)

You can install these packages by launching R (or RStudio) and running:


## Methodology

1. Cointegration Check (Engle-Granger)
  We test whether Crude and Gasoline share a stable, long-run relationship.
  If the ADF test on residuals is significant, we confirm cointegration.
2. Four Forecasting Models
 - ECM (Error Correction Model)
  Uses the cointegration relationship to model short-term changes in gasoline prices relative to crude prices.
 - VECM (Vector Error Correction Model)
  A multivariate generalization that handles both variables (gasoline and crude) in a cointegrated system.
 - ARIMAX
  A univariate ARIMA on Gasoline prices that includes external regressors (Crude and other exogenous variables).
 - LSTM
  A neural network approach that uses sequences of past data to predict future Gasoline prices. We feed in multiple lags of Crude/Gasoline to learn patterns.
3. Spread-Based Trading
 - Spread = Gasoline−β×Crude or simply (Predicted Gasoline – Actual Crude).
 - We standardize or compute a z-score relative to historical mean & std.
 - Signals:
    - Buy if spread < (mean – 1.5 SD)
    - Sell if spread > (mean + 1.5 SD)
    - Hold otherwise
      
We simulate trades in the test period (2024) to see the cumulative profit from each model’s forecasted spread.


## Results



## Conclusion
