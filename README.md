# Algorithmic Trading Strategy on Zillow Group Inc. (ZG)

## Overview
This project develops and evaluates an algorithmic trading strategy for **Zillow Group Inc. (ZG)** stock. The strategy combines **MACD**, **RSI** and other indicators to identify optimal buy and sell signals and contructed strategy. The model is backtested on historical data from January 1, 2018, to January 1, 2024, and further validated using bootstrap resampling techniques. This is the final project for NYU FRE-7251 High Frequency Trading course, writen by Shangqing Zhuang.

## Methodology

### 1. Technical Indicators
The trading strategy relies on two key indicators:**MACD** and **RSI**.

### 2. Signal Generation
- **Buy Signal**: `MACD > Signal Line` **AND** `RSI > 70`
- **Sell Signal**: `MACD < Signal Line` **AND** `RSI < 20`
- After a **sell signal**, a **cooling-off period of 5 days** is implemented before allowing new buy signals.

### 3. Backtesting & Performance Evaluation
The strategy is tested on historical price data to measure performance.

A **one-sample t-test** is used to validate that the mean return is significantly different from zero.

### 4. Bootstrap Resampling
- To test model robustness, an **AR(1) model with OLS regression** is used to generate **200 resampled price series**.
- The strategy is applied to each sample to compare performance against the historical dataset.
