# Realtime-stock-price-analysis
# Real-Time Stock Price Analysis

This project fetches real-time stock data using Yahoo Finance API, analyzes stock trends with moving averages, and visualizes the data.

## Features
- Fetches live stock data
- Computes 10-period and 50-period moving averages
- Visualizes stock price trends

## Requirements
- Python 3.x
- Libraries: `yfinance`, `pandas`, `matplotlib`

## How to Run
1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt

   import yfinance as yf
import matplotlib.pyplot as plt

# Get ticker symbol from user
ticker = input("Enter stock ticker symbol: ").upper()

# Fetch stock data
stock = yf.Ticker(ticker)
data = stock.history(period='1d', interval='1m')

# Plot stock price
plt.figure(figsize=(10, 5))
plt.plot(data['Close'], label=f'{ticker} Closing Price')
plt.title(f'Real-time Stock Price for {ticker}')
plt.xlabel('Time')
plt.ylabel('Price')
plt.legend()
plt.show()

