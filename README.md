# Crude Gasoline Dynamics: Cointegration Forecasting for Energy Arbitrage

Welcome to our Time Series Forecasting repository, where we analyze and compare the performance of ECM, VAR, ARIMAX, and LSTM models for predicting gasoline prices. This project applies econometric and deep learning approaches to assess forecasting accuracy and profitability.


## Project Overview
This repository includes a structured time series forecasting analysis, focusing on different statistical and machine learning models. The analysis is divided into the following components:

1️⃣ Exploratory Data Analysis (EDA) – Visualizing trends, seasonality, and statistical properties.

2️⃣ ECM, VAR, and ARIMAX Models – Implemented in R Markdown and compiled into a PDF and HTML report.

3️⃣ LSTM Model – Implemented in Jupyter Notebook (Python) with an HTML output.

4️⃣ Results & Conclusion – Comparing model performance and cumulative profits.

This modular structure ensures efficient collaboration, allowing different components to be worked on independently while producing a unified analysis.

## Repository Structure'
```
.
├── time_series_models.qmd      # R Markdown file (ECM, VAR, ARIMAX)
├── time_series_models.pdf      # PDF report (ECM, VAR, ARIMAX)
├── time_series_models.html     # HTML report (ECM, VAR, ARIMAX)
├── lstm_model.ipynb            # Jupyter Notebook (LSTM)
├── lstm_model.html             # HTML report (LSTM)
├── render.sh                   # Script to generate reports
└── docs/                       # Contains rendered HTML, PDF, and supporting files
```

## Introduction
The relationship between gasoline and crude oil prices has long been recognized as a crucial indicator in energy markets, primarily due to their inherent cointegration. This close relationship exists because Gasoline is a refined derivative of Crude Oil. Understanding and leveraging this relationship allows traders and stakeholders to optimize their decision-making and profitability. In this project, we analyzed historical gasoline and crude oil pricing data to explore their cointegration characteristics thoroughly. We employed four distinct forecasting models to predict gasoline prices for the year 2024:


1. ECM (Error Correction Model)
2. VAR (Vector Autoregression):
3. ARIMAX (Auto-Regressive Integrated Moving Average with eXogenous Variables)
4. LSTM (Long Short-Term Memory):


Using these predictions, we developed tailored pricing strategies designed for effective trading. Subsequently, we evaluated the efficacy of each forecasting approach by calculating and comparing their respective profitability, providing valuable insights into model performance and the strategic implications for trading in energy commodities. We also hypothesize that LSTM will have the ability to capture the intricate collinear relationship between crude oil and gasoline prices most effectively.

