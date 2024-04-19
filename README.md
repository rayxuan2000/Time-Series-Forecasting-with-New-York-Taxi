# Time-Series-Forecasting-with-Yahoo-Stock-Price

## Introduction
This project mainly focuses on the principle and application of time series theory. I used a classic dataset about stock price to implement on. 

## Code and Data
You can find them in the same repo as this readme file.

[Data source](https://finance.yahoo.com/)

## Summary
- Used Yahoo’s stock price from 2015 to 2020 (data size = 1825) as a time series for analysis and forecasting via **Python**.
- Implemented exploratory data analysis in visualization, shifted time series data to find varying rate and confirmed high
correlation between high, low, open and close attribute.
- Performed frequency conversion with downsampling method (3 days) for wider time frame.
- Plotted autocorrelation (tails o↵) and partial autocorrelation function (cuts o↵ at lag 2) to prepare for modeling.
- Decomposed time series data into additive trend, seasonal and residual component to know the pattern.
- Trained ARIMA model (p=2, d=2, q=1 ) using original data, performed in-sample prediction (MSE = 1365.23) and
out-of-sample prediction (MSE = 61618.47) to compare the di↵erence.
