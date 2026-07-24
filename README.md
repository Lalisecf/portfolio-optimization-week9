# 📈 Portfolio Optimization Using Time Series Forecasting

## 10 Academy – Artificial Intelligence Mastery Program

### Week 9 Challenge

**Author:** Lalise Fufi

---

# Project Overview

This project was completed as part of the **10 Academy Artificial Intelligence Mastery Program – Week 9 Challenge**.

The objective is to develop a complete data-driven investment decision support system for **Guide Me in Finance (GMF) Investments** by integrating financial time series forecasting, portfolio optimization, and backtesting.

Historical market data were collected using the **Yahoo Finance (YFinance) API** for three representative financial assets:

- **Tesla (TSLA)** – High-growth, high-risk technology stock
- **Vanguard Total Bond Market ETF (BND)** – Low-risk bond ETF
- **SPDR S&P 500 ETF (SPY)** – Diversified U.S. equity ETF

The project follows an end-to-end quantitative investment workflow consisting of:

- Historical data collection and preprocessing
- Exploratory Data Analysis (EDA)
- Financial risk analysis
- Time series forecasting using ARIMA and LSTM
- Twelve-month market forecasting
- Portfolio optimization using Modern Portfolio Theory (MPT)
- Efficient Frontier analysis
- Portfolio backtesting against a benchmark
- Investment recommendation based on forecasted market behavior

---
# Business Objective

Guide Me in Finance (GMF) Investments aims to enhance portfolio management by combining machine learning forecasting techniques with quantitative portfolio optimization.

The primary objectives are to:

- Analyze historical market behavior
- Forecast future Tesla stock prices
- Compare statistical and deep learning forecasting models
- Build an optimal investment portfolio
- Evaluate portfolio performance through historical backtesting
- Generate data-driven investment recommendations

---

# Project Structure

```text
portfolio-optimization/
│
├── .github/
│   └── workflows/
│       └── unittests.yml
│
├── data/
│   ├── raw/
│   │   ├── TSLA.csv
│   │   ├── BND.csv
│   │   └── SPY.csv
│   │
│   └── processed/
│       ├── task3_forecast_results.csv
│       ├── optimal_portfolio_weights.csv
│       └── backtest_results.csv
│
├── notebooks/
│   ├── task1_eda.ipynb
│   ├── task2_forecasting.ipynb
│   ├── task3_future_forecasting.ipynb
│   ├── task4_portfolio_optimization.ipynb
│   └── task5_backtesting.ipynb
│
├── src/
├── scripts/
├── tests/
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

# Dataset

Historical market data were downloaded directly from **Yahoo Finance** using the **YFinance** Python package.

## Assets

| Asset | Ticker | Risk Profile |
|--------|--------|--------------|
| Tesla | TSLA | High Risk |
| Vanguard Total Bond Market ETF | BND | Low Risk |
| SPDR S&P 500 ETF | SPY | Moderate Risk |

## Time Period

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
- pmdarima
- TensorFlow / Keras
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

Two financial risk metrics were calculated.

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

# Task 2: Time Series Forecasting

## Objectives

The second task focuses on developing, training, and evaluating forecasting models to predict Tesla's future stock prices.

Two forecasting approaches were implemented:

- ARIMA (AutoRegressive Integrated Moving Average)
- Long Short-Term Memory (LSTM) Neural Network

The models were compared using standard forecasting performance metrics.

---

## Data Preparation

Before model training:

- Tesla closing prices were selected as the target variable.
- The dataset was divided chronologically.
- Training data covered **2015–2024**.
- Testing data covered **2025–2026**.
- Random shuffling was avoided to preserve the temporal order of observations.

---

## ARIMA Model

The statistical forecasting model was developed using:

- Auto ARIMA for automatic parameter selection
- ACF (Autocorrelation Function) plots
- PACF (Partial Autocorrelation Function) plots
- Optimal (p, d, q) parameter estimation
- Model fitting on training data
- Forecast generation on the testing period

The model captures linear relationships in historical stock prices and provides an interpretable baseline forecasting model.

---

## LSTM Model

A deep learning forecasting model was implemented using TensorFlow/Keras.

The workflow included:

- Min-Max scaling
- 60-day input sequences
- Two stacked LSTM layers
- Dropout regularization
- Dense output layer
- Model training using the Adam optimizer
- Prediction on unseen testing data

LSTM is capable of learning complex nonlinear temporal relationships within stock price movements.

---

## Model Evaluation

Both models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

A comparison table summarizes the forecasting performance of the two models and supports selecting the best-performing model for future forecasting.

---

## Forecasting Workflow

The forecasting pipeline consists of:

1. Load Tesla historical data
2. Chronological train-test split
3. Build ARIMA model
4. Generate ARIMA forecasts
5. Prepare LSTM sequences
6. Train the LSTM network
7. Generate LSTM predictions
8. Compare forecasting performance
9. Select the best-performing model

---

# Task 3 — Future Market Forecasting

## Objectives

Task 3 extends the selected forecasting model to predict Tesla's future stock prices over the next twelve months.

The objective is to generate actionable forecasts that support investment decision-making.

---

## Completed Analyses

- Retrained the best-performing forecasting model using the full historical dataset
- Generated a 12-month Tesla stock price forecast
- Produced test-period predictions for model validation
- Visualized historical prices, test predictions, and future forecasts
- Estimated 95% confidence intervals
- Evaluated confidence interval growth over time
- Calculated forecast summary statistics
- Generated monthly forecast values
- Analyzed expected monthly returns
- Compared forecast prices with the last observed market price
- Identified market opportunities and investment risks
- Discussed forecast reliability and uncertainty

---

## Key Findings

- Tesla is expected to maintain a long-term upward trend.
- Forecast uncertainty increases gradually over longer horizons.
- Confidence intervals widen over time, reflecting increased forecasting uncertainty.
- The forecast suggests continued long-term growth while highlighting the importance of managing forecast risk.

---

# Task 4 — Portfolio Optimization

## Objectives

Task 4 combines forecasted returns with historical asset behavior to construct an optimal investment portfolio using Modern Portfolio Theory (MPT).

---

## Completed Analyses

- Estimated expected annual returns
- Incorporated forecasted Tesla return into optimization
- Computed covariance matrix
- Generated covariance and correlation heatmaps
- Constructed Efficient Frontier
- Simulated thousands of random portfolios
- Identified Maximum Sharpe Ratio portfolio
- Identified Minimum Volatility portfolio
- Visualized portfolio allocation
- Evaluated portfolio return contribution
- Evaluated portfolio risk contribution
- Compared optimal portfolios
- Generated investment recommendation

---

## Key Findings

- The Maximum Sharpe portfolio achieved the best balance between expected return and portfolio risk.
- Diversification significantly reduced portfolio risk.
- Forecasted Tesla returns improved expected portfolio performance.
- Efficient Frontier analysis identified portfolios offering optimal risk-return trade-offs.

---

# Task 5 — Portfolio Backtesting

## Objectives

Task 5 evaluates how the optimized portfolio would have performed historically by comparing it with a benchmark portfolio.

---

## Completed Analyses

- Portfolio backtesting using historical market data
- Monthly portfolio rebalancing
- Benchmark comparison (60% SPY / 40% BND)
- Cumulative return analysis
- Portfolio growth simulation
- Rolling Sharpe Ratio
- Maximum Drawdown analysis
- Monthly return comparison
- Active return analysis
- Tracking Error
- Information Ratio
- Win Rate analysis
- Performance summary table
- Strategy performance visualization
- Investment recommendation based on backtest results

---

## Performance Metrics

The following metrics were evaluated:

- Total Return
- Annualized Return
- Annualized Volatility
- Sharpe Ratio
- Maximum Drawdown
- Tracking Error
- Information Ratio

---

## Key Findings

- The optimized portfolio outperformed the benchmark in cumulative returns.
- Portfolio optimization improved risk-adjusted performance.
- Diversification reduced downside risk.
- Backtesting demonstrated the robustness of the proposed investment strategy.
- The optimized portfolio consistently achieved a superior balance between return and volatility.

---

# Project Workflow

```text
Historical Market Data
          │
          ▼
 Data Cleaning & EDA
          │
          ▼
 Risk Analysis
          │
          ▼
 Time Series Forecasting
 (ARIMA & LSTM)
          │
          ▼
 Best Model Selection
          │
          ▼
 12-Month Forecast
          │
          ▼
 Portfolio Optimization
 (Modern Portfolio Theory)
          │
          ▼
 Efficient Frontier
          │
          ▼
 Portfolio Backtesting
          │
          ▼
 Final Investment Recommendation
```

---

# Requirements

Install all required dependencies:

```bash
pip install -r requirements.txt
```

---

# Running the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Run the notebooks sequentially:

1. `task1_eda.ipynb`
2. `task2_forecasting.ipynb`
3. `task3_future_forecasting.ipynb`
4. `task4_portfolio_optimization.ipynb`
5. `task5_backtesting.ipynb`

Each notebook builds on the outputs of the previous task.

---

# Repository Progress

## ✅ Completed

- Project setup
- Historical market data extraction
- Data preprocessing
- Exploratory Data Analysis
- Financial risk analysis
- Stationarity testing
- ARIMA forecasting
- LSTM forecasting
- Forecast model comparison
- 12-month market forecasting
- Forecast uncertainty analysis
- Portfolio optimization
- Efficient Frontier analysis
- Monte Carlo portfolio simulation
- Portfolio allocation recommendation
- Portfolio backtesting
- Benchmark comparison
- Performance evaluation
- Investment recommendation
- Documentation

---

# References

- Yahoo Finance (YFinance API)
- PyPortfolioOpt Documentation
- TensorFlow Documentation
- Statsmodels Documentation
- Scikit-learn Documentation
- Pandas Documentation
- NumPy Documentation
- Matplotlib Documentation
- Seaborn Documentation

---

# Author

**Lalise Fufi**

10 Academy – Artificial Intelligence Mastery Program

**Week 9 Challenge – Portfolio Optimization Using Time Series Forecasting**

2026