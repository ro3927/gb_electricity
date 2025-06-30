GB Electricity Market - Intraday Trading Strategy
This project presents a comprehensive approach to designing and backtesting intraday trading strategies on the Great Britain (GB) electricity market. The work was developed as part of the KRITI 2025 competition under the "Low Prep" category by Hostel 57.

**Objective**

To analyze intraday electricity price patterns from 2022–2024 and develop machine learning-driven and rule-based trading strategies that exploit price volatility caused by renewable generation, demand fluctuations, and imbalance signals.

**Dataset**

Data was sourced primarily via the Elexon API, containing:

* Wind & Solar Generation Forecasts (Day-ahead)
* Electricity Demand Forecasts
* Market Index Prices (MIP)
* Temperature Data (Hourly)
* Net Imbalance Volume (NIV)
* 48 Settlement Periods/day

**Data Processing**

* Aligned data across settlement periods and merged forecasts
* Handled anomalies like DST transitions, holidays, and missing values
* Engineered features including lags, rolling stats, price-demand interactions

**Strategies Implemented**

CUSUM-Based Strategy:

* Detects regime shifts (bullish/bearish) using CUSUM
* Conditions include volume, price discount, and demand surges
* Buy/sell based on cumulative deviations from rolling mean

ML-Based Strategy:

* Random Forest predicts next-period price direction
* Compared against XGBoost and Ridge (selected based on MAE)
* Executes trades on model signals with Sharpe ratio analysis

Time-Based Strategy:

* Trades at specific settlement periods with volatility and regime filters
* Incorporates Markov-Switching Models (MSM) for volatility regimes

*Volatility Detection

Markov Switching Model (MSM): Identifies high/low volatility states

PCA + K-Means: Unsupervised volatility clustering for market segmentation

*Performance Metrics

Initial Balance: 10,000
Final Balance: 240,743.89
Net Return: 2,307.44%
Max Drawdown: -21.30%
Max PnL: 100,490.84
Annualized Return: \~34M%
Total Transaction Fees: 0

*Technologies Used

Python, Pandas, Scikit-learn, Statsmodels
Matplotlib, Seaborn, Plotly
Elexon API for data


*References

* Pozzetti (2020). Algorithmic Trading in UK Power Markets
* Hamilton, J.D. (1989). A New Approach to the Economic Analysis of Nonstationary Time Series
* Elexon API Documentation


