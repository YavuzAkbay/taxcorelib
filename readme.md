# Technical Analysis Library

This library provides a collection of technical analysis indicators for financial market analysis. It is implemented in Python using the NumPy and Pandas libraries. The indicators can be used for various trading strategies and technical analysis applications.

## Features

- Simple Moving Average (SMA)
- Exponential Moving Average (EMA)
- Average True Range (ATR)
- Bollinger Bands
- Relative Strength Index (RSI)
- Moving Average Convergence Divergence (MACD)
- And many more...

## Installation

To use this library, ensure you have Python installed along with the required libraries. You can install the dependencies using pip:
```
pip install numpy pandas taxcore
```
## Usage
```bash
import numpy as np
import pandas as pd
import yfinance as yf
from TAxCore import TechnicalAnalysis

# Download historical price data for a stock (e.g., Apple)
ticker = 'AAPL'
data = yf.download(ticker, start='2022-01-01', end='2023-01-01')

# Extract closing prices using Numpy and ensure it's 1D
prices = data['Close'].to_numpy().flatten()

# Calculate Simple Moving Average (SMA)
sma_values = TechnicalAnalysis.sma(prices, period=20)
print("SMA Values:", sma_values)

# Calculate Exponential Moving Average (EMA)
ema_values = TechnicalAnalysis.ema(prices, length=20)
print("EMA Values:", ema_values)

# Calculate Bollinger Bands
basis, upper, lower = TechnicalAnalysis.bollinger_bands(prices, length=20)
print("Bollinger Bands - Basis:", basis, "Upper:", upper, "Lower:", lower)

# Calculate Relative Strength Index (RSI)
rsi_values = TechnicalAnalysis.rsi(prices, period=14)
print("RSI Values:", rsi_values)

# Calculate Moving Average Convergence Divergence (MACD)
macd_line, signal_line, histogram = TechnicalAnalysis.macd(prices)
print("MACD Line:", macd_line, "Signal Line:", signal_line, "Histogram:", histogram)

# For visualization I recommend either Matplotlib, Plotly or MPLFinance. I tried all and they all work pretty good.
