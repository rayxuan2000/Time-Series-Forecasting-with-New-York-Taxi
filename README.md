# Time-Series-Forecasting-with-New-York-Taxi

## Introduction
This project mainly focuses on the principle and application of time series theory. I used New York taxi data to implement on. 

## Code and Data
You can find them in the same repo as this readme file.

[Data source](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

[Dashboard](https://public.tableau.com/app/profile/ruize.xuan/viz/taxi_17164222813720/1_1)


## Notes
- In the EDA stage, I implemented several techniques such as varying rate, rolling mean and cumulative mean to explore more details. To make time series model more efficient and time-saving, I resampled the original data.
- Recall the definition of **ACF** and **PACF**. ACF: includes all the lags or intervals between t and t-k time period; actually is self correlation coefficient. PACF: doesn't take into account all the time lags between t and t-k. Also imagine these two plots in your head with confidence interval and statistical significance.
- Although some advanced models don't require time series data to have stationary property (eg. built-in mechanisms to handle non-stationary data through differencing), we'd better check this before applying some non-advanced model. One of the most common way of doing this is **ADF test**. It mainly use hypothesis testing idea. Assume it's non-stationary...
- About **differencing**: Rule 1: If the series has positive autocorrelations out to a high number of lags, then it probably needs a higher order of differencing. Rule 2: If the lag-1 autocorrelation is zero or negative, or the autocorrelations are all small and patternless, then the series does not need a higher order of  differencing. If the lag-1 autocorrelation is -0.5 or more negative, the series may be overdifferenced.  BEWARE OF OVERDIFFERENCING!! One symptom of possible overdifferencing is an increase in the standard deviation.
- Use ACF and PACF plots to determine param of models.
- Models used in this project: AR, MA, ARMA, ARIMA. 
  
## Summary
- Developed a Python workflow for collecting, cleaning, storing, and analyzing over 10GB of New York cab trip records
from 2010 to 2024, and created Tableau dashboards to visualize the data and support decision-making at higher levels.
- Conducted exploratory data analysis, including component decomposition, rate of change, sliding averages, and downsam-
pling; performed ADF stability testing and differential smoothing.
- Generated autocorrelation and partial autocorrelation plots, fine-tuned and compared multiple time series models, reduc-
ing the Akaike Information Criterion (AIC) by approximately 12%.
- Proposed and validated a hypothesis testing model for cab passenger flow using external data and Poisson regression,
establishing a significant correlation between passenger flow and commercial activities.
