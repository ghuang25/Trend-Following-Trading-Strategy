# Trend-Following Trading Strategy

## Project Overview

This project implements a trend-following trading strategy using stock market data fetched from the Alpha Vantage API. The goal of this strategy is to use **simple moving averages (SMA)** to identify buy and sell signals based on crossovers between short-term and long-term trends in the stock price. The notebook simulates how an algorithmic trading system might execute trades based on these signals, and it provides users with a visual representation of price trends and trading actions.

## Purpose

**Educational Tool**:
This notebook serves as a practical example for those interested in learning about algorithmic trading, financial data analysis, and the use of APIs to fetch real-time stock data. It provides an accessible way for beginners to understand the mechanics behind automated trading strategies and technical indicators.

**Trading Strategy Testing**:
It allows users to experiment with a basic trading strategy, showing how moving averages can inform trading decisions. By running the notebook, users can see how simple strategies are backtested and gain insight into their potential effectiveness over a given time period.

**Data Analysis**:
The notebook demonstrates how to collect, manipulate, and visualize financial data, helping users gain a deeper understanding of stock market trends and price movements. The plotted charts give a clear view of how prices evolve and how trading signals are generated.

## Steps and Methodology

1. **Stock Data Fetching**:

The notebook fetches real-time stock data from the Alpha Vantage API based on the user's input:

* **Stock symbol** (e.g., AAPL for Apple Inc.)
* **Time series type** (intraday, daily, etc.)
* **Output size** (compact or full)
* **Interval** (if intraday time series is chosen)

Once fetched, the data is organized into a ```pandas``` DataFrame containing the following columns:

  * Timestamp
  * Open price
  * High price
  * Low price
  * Close price
  * Volume

2. **Data Preprocessing**:

The fetched data is processed to prepare it for analysis:

* **Timestamps** are converted to ```datetime``` objects.
* **Open**, **high**, **low**, **close prices**, and **volume** data are extracted and stored in separate columns of the DataFrame.

3. **Simple Moving Averages (SMAs)**:

Two SMAs are calculated:

* **50-day SMA (Short-Term)**: The average closing price over the last 50 data points.
* **200-day SMA (Long-Term)**: The average closing price over the last 200 data points.

These moving averages are key to identifying market trends and making trading decisions.

4. **Trading Signals**:

Trading signals are generated based on a **crossover strategy**:

* A **buy signal** is triggered when the 50-day SMA crosses above the 200-day SMA, signaling a potential upward trend.
* A **sell signal** is triggered when the 50-day SMA crosses below the 200-day SMA, signaling a potential downward trend.

These signals guide the backtesting of the strategy by simulating trades over the selected time period.

5. **Backtesting the Strategy**:

Backtesting is performed using the following steps:

* The user enters an initial capital amount.
* When a buy signal is detected, the capital is used to buy shares.
* When a sell signal is detected, all shares are sold, and the capital is updated.

The final portfolio value is calculated at the end of the backtest, representing the strategy's performance.

6. **Visualization**:

The notebook visualizes the following:

* **Stock price**: A line plot showing the price evolution over time.
* **50-day and 200-day SMAs**: Lines representing the short-term and long-term trends.
* **Buy and sell signals**: Green and red markers indicating when to buy and sell based on the crossover strategy.

A sample visualization is provided to help users understand how the price, SMAs, and signals interact over time.

7. **Results**:

The output consists of a chart displaying the stock's price, the short-term (50-day) and long-term (200-day) SMAs, and the corresponding buy/sell signals.

**Example Results**:
* **Price Movement**: Shows clear fluctuations in the stock's value over time.
* **Buy Signals**: Indicated by green dots, representing points where the short-term SMA crosses above the long-term SMA.
* **Sell Signals**: Indicated by red dots, representing points where the short-term SMA crosses below the long-term SMA.

After backtesting, the notebook prints the initial capital and the final portfolio value, allowing the user to assess the success of the strategy over the selected time period.

## How to Run the Project

### Requirements
Before running the project, ensure you have the following libraries installed:

* Python 3.x
* pandas
* numpy
* matplotlib
* requests (for API interaction)

You can install the required libraries via ```pip```:

```
pip install pandas numpy matplotlib requests
```
### Steps to Execute the Program
1. Clone the repository and navigate to your project directory:
```
git clone https://github.com/ghuang25/Trend-Following-Trading-Strategy.git
```
2. Set up an Alpha Vantage account and obtain an API key.

3. Run the Python script:
```
python program.py
```
4. Follow the prompts:
* Enter your Alpha Vantage API key.
* Provide the stock symbol, time series type, and other required inputs.

The program will fetch the data, backtest the strategy, and display the final portfolio value. A plot will also be generated to visualize the price, SMAs, and trading signals.
