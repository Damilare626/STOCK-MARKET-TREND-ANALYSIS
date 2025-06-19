# STOCK-MARKET-TREND-ANALYSIS
**PROJECT OVERVIEW**
**Objective**
To analyze historical stock price data and identify trends, volatility, and predictive insights for selected stocks. This project focuses on visualizing market behavior, comparing company performance, and exploring basic forecasting techniques.

**Project Structure**

---

_Pyton_
`
stock-market-trend-analysis/├── data/
│   └── stock_data.csv
├── notebooks/
│   └── stock_analysis.ipynb
├── scripts/
│   └── data_fetcher.py
├── outputs/
│   └── trend_plots/
├── README.md
└── requirements.txt `

---

**Data Source**
  *  Yahoo Finance using Python’s yfinance package or directly from CSV files.
  *  Example stock symbols: AAPL, GOOGL, MSFT, TSLA, AMZN

**Tools & Technologies**
  *  Python
  *  Libraries: pandas, matplotlib, seaborn, yfinance, numpy, plotly, statsmodels
  *  Optional: Prophet or ARIMA for time series forecasting

**Analysis Tasks**
1. Data Collection
    * Fetch historical daily data (e.g., 2018–2024)
    * Extract: Open, Close, High, Low, Volume, Date

---

_Pyton_
`
import yfinance as yf
tickers = ['AAPL', 'MSFT', 'GOOGL']
data = yf.download(tickers, start='2018-01-01', end='2024-12-31')['Adj Close']
data.to_csv('data/stock_data.csv') `

---

2.  Exploratory Data Analysis (EDA)
  *  Plot stock prices over time
  *  Compare % return between companies
  *  Calculate moving averages (50-day, 200-day)
  *  Identify market corrections or crashes

---

_Pyton_
`
import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv("data/stock_data.csv", index_col=0, parse_dates=True)
df.plot(figsize=(12, 6), title="Stock Price Over Time")
plt.show() `

---

3. Volatility & Correlation
  *  Daily return percentage
  *  Rolling standard deviation
  *  Correlation heatmap between stocks returns

---

_Pyton_
`
= df.pct_change().dropna()
returns.std()  # Volatility
returns.corr()  # Correlation between stocks`

---

4. Technical Indicators
  * Simple Moving Average (SMA)
  * Relative Strength Index (RSI)
  * MACD (Moving Average Convergence Divergence)
5. Forecasting (Optional)
  * Predict next month’s price using Prophet or ARIMA
  * Split data: train/test
  * Evaluate: RMSE or MAPE

**Key Findings (Example Output)**
  * Apple and Microsoft showed consistent upward trends post-2020.
  * Tesla displayed high volatility compared to others.
  * AAPL and MSFT had the highest correlation (~0.85).
  * Market dips observed during March 2020 and early 2022.

**Visualization Examples**
  * Line chart of adjusted close prices
  * Heatmap of stock correlations
  * Rolling volatility chart
  * Forecasted vs actual stock price

**Conclusion**

This project demonstrates how to:
  * Clean and manipulate stock data
  * Understand market behavior over time
  * Compare companies quantitatively
  * Apply basic forecasting methods for price prediction








