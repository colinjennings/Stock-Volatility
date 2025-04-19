
# LSTM Model for Stock Volatility Prediction

## Objective
- Predict future **stock volatility** based on historical trends and earnings report timelines.
- Investigate whether volatility increases in anticipation of earnings announcements.

## Why LSTM?
- LSTM (Long Short-Term Memory) is a special type of **Recurrent Neural Network (RNN)**.
- It excels at learning from **time-series data**, making it ideal for modeling stock price sequences.
- Capable of capturing **long-term dependencies** and temporal trends.

## Dataset Overview
- Collected **5 years** of data (2020–2025) for **50 S&P 500 companies**.
- Used `yfinance` to pull historical stock data: Open, High, Low, Close, Volume.
- Scraped tickers from Wikipedia’s S&P 500 list.

## Feature Engineering
- Calculated technical indicators like:
  - **Returns** (log returns)
  - **Volatility** (rolling standard deviation)
  - **Relative Strength Index (RSI)** over a 14-day window
- Normalized all time-series data for model compatibility.

## Model Architecture
- Input: 10-day sliding window of engineered features
- Output: One-step ahead **volatility prediction**
- Built using **Keras** with TensorFlow backend

## Training Setup
- Loss Function: Mean Squared Error (MSE)
- Optimizer: Adam
- Batch size and epochs were tuned for performance
- Used dropout and early stopping to avoid overfitting

## Key Observations
- LSTM detected **volatility spikes** just before earnings dates
- Outperformed **Linear Regression** baseline in prediction accuracy
- Validated hypothesis: **investor expectation** drives short-term volatility

## Conclusion
- LSTM is effective in capturing time-based volatility patterns
- Future improvements can include:
  - Incorporating **news sentiment**
  - Expanding to more tickers
  - Exploring **multi-step forecasting**
