# Time-Series-Forecasting-with-Yahoo-Stock-Price

## Introduction
This project mainly focuses on the principle and application of time series theory. I used a classic dataset about stock price to implement on. 

## Code and Data
You can find them in the same repo as this readme file.

[Data source](https://finance.yahoo.com/)

## Summary
- Used Yahoo’s stock price from 2015 to 2020 (data size = 1825) as a time series for analysis and forecasting via **Python**.
- Conducted exploratory data analysis with a focus on visualizations including **component decomposition**, **temporal variations** and **downsampling method** etc. to comprehend the dynamics of the stock price data.
- Generated **autocorrelation** (tails off) and **partial autocorrelation** (cuts off at lag 2) plots to guide model selection.
- Fine-tuned **ARIMA model** (p=2, d=2, q=1) using original data and **cut down prediction MSE** more than 60000 by substituting out-of-sample prediction (MSE = 61618.47) with in-sample prediction (MSE = 1365.23).
