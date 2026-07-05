# 📈 Portfolio Optimization Using Time Series Forecasting

## 10 Academy – Artificial Intelligence Mastery Program

### Week 9 Challenge

**Author:** Lalise Fufi

---

# Project Overview

This project is part of the **10 Academy Artificial Intelligence Mastery Program – Week 9 Challenge**.

The objective is to analyze historical financial market data and develop a data-driven portfolio optimization strategy for **Guide Me in Finance (GMF) Investments**.

Historical financial data for three assets were collected using the **YFinance API**:

- **Tesla (TSLA)** – High-growth, high-risk stock
- **Vanguard Total Bond Market ETF (BND)** – Low-risk bond ETF
- **SPDR S&P 500 ETF (SPY)** – Diversified equity ETF

The complete project consists of:

- Data preprocessing and exploratory data analysis
- Time series forecasting using ARIMA/SARIMA and LSTM
- Future market forecasting
- Portfolio optimization using Modern Portfolio Theory (MPT)
- Portfolio backtesting

This repository currently contains the implementation of **Task 1**, which focuses on data extraction, preprocessing, exploratory data analysis, stationarity testing, and risk analysis.

---

# Business Objective

Guide Me in Finance (GMF) Investments aims to improve portfolio management through predictive analytics and quantitative financial analysis.

The goal of this project is to analyze historical market behavior, identify statistical characteristics of different asset classes, and prepare clean financial data for forecasting and portfolio optimization.

---

# Project Structure

```
portfolio-optimization/
│
├── .github/
│   └── workflows/
│
├── .vscode/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── task1_eda.ipynb
│   └── README.md
│
├── scripts/
│
├── src/
│
├── tests/
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

# Dataset

Historical market data were downloaded directly from **Yahoo Finance** using the **YFinance** Python package.

### Assets

| Asset | Ticker | Risk Profile |
|--------|--------|--------------|
| Tesla | TSLA | High Risk |
| Vanguard Total Bond Market ETF | BND | Low Risk |
| SPDR S&P 500 ETF | SPY | Moderate Risk |

### Time Period

**January 1, 2015 – June 30, 2026**

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- YFinance
- Statsmodels
- Scikit-learn
- Jupyter Notebook

---

# Task 1: Data Preprocessing and Exploratory Data Analysis

## Objectives

The first task focuses on understanding the financial data before building forecasting models.

The following analyses were completed:

- Download historical financial data
- Data inspection
- Data cleaning
- Missing value handling
- Summary statistics
- Data normalization
- Closing price visualization
- Daily return analysis
- Rolling mean analysis
- Rolling standard deviation analysis
- Outlier detection
- Highest and lowest daily return analysis
- Augmented Dickey-Fuller (ADF) stationarity testing
- Value at Risk (VaR)
- Sharpe Ratio calculation

---

# Exploratory Data Analysis

The notebook includes several visualizations, including:

- Historical closing prices
- Daily return plots
- Rolling mean and rolling standard deviation
- Boxplots for outlier detection

These visualizations help compare the behavior of TSLA, BND, and SPY over the study period.

---

# Key Findings

## Closing Price Analysis

- Tesla experienced rapid long-term growth with significant price fluctuations.
- BND remained relatively stable throughout the study period.
- SPY showed consistent long-term growth with moderate volatility.

---

## Daily Returns

- Tesla exhibited the highest daily volatility.
- BND produced the smallest daily fluctuations.
- SPY maintained moderate day-to-day variability.

---

## Rolling Statistics

The rolling statistics indicate:

- Tesla has the highest rolling volatility.
- BND remains stable over time.
- SPY demonstrates sustained growth with moderate risk.

---

## Outlier Detection

Boxplots revealed:

- Numerous extreme returns for Tesla.
- Very few outliers for BND.
- Moderate outliers for SPY.

---

## Stationarity Test

The Augmented Dickey-Fuller (ADF) test showed:

- Closing prices are generally non-stationary.
- Daily returns are stationary.

These findings indicate that daily returns are more suitable for time series forecasting models such as ARIMA.

---

## Risk Metrics

Two financial risk metrics were calculated:

### Value at Risk (VaR)

The 5% historical Value at Risk estimates the maximum expected daily loss.

Results showed:

- TSLA has the highest downside risk.
- BND has the lowest downside risk.
- SPY falls between the two.

### Sharpe Ratio

The Sharpe Ratio measures risk-adjusted return.

The comparison helps determine which asset provides the highest return relative to its level of risk.

---

# Data Cleaning

The following preprocessing steps were performed:

- Verified data types
- Checked missing values
- Filled missing observations using forward fill and backward fill
- Calculated daily returns
- Generated rolling statistics
- Normalized closing prices where appropriate

---

# Requirements

Install the required packages using:

```bash
pip install -r requirements.txt
```

---

# Running the Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```
notebooks/task1_eda.ipynb
```

Run all cells sequentially.

---

# Repository Progress

## ✅ Completed

- Project structure
- Historical data extraction
- Data preprocessing
- Exploratory Data Analysis
- Stationarity testing
- Risk metrics
- Documentation

## 🚧 Upcoming Tasks

- Task 2: Time Series Forecasting (ARIMA/SARIMA & LSTM)
- Task 3: Future Market Forecasting
- Task 4: Portfolio Optimization using Modern Portfolio Theory
- Task 5: Portfolio Backtesting

---

# References

- Yahoo Finance (YFinance API)
- Pandas Documentation
- NumPy Documentation
- Matplotlib Documentation
- Seaborn Documentation
- Statsmodels Documentation

---

# Author

**Lalise Fufi**

10 Academy Artificial Intelligence Mastery Program

Week 9 Challenge

2026