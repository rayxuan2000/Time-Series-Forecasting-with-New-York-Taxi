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
- Use ACF and PACF plots to determine param of models. If PACF tails off and ACF cuts off then determine MA otherwise AR.
- Models used in this project: AR, MA, ARMA, ARIMA. AR use previous values, MA use previous errors, ARMA combines the two and ARIMA introduce differencing.
- About **AIC**: AIC, or the Akaike Information Criterion, is a measure of the goodness of fit of a statistical model. It takes into account both the model's likelihood and its complexity, providing a balance between accuracy and simplicity. In time series analysis, AIC is commonly used to compare different models and select the most appropriate one for time series forecasting. AIC=2k−2ln(L) where k is number of parameters and L is likelihood function.
- I hypothesize that there is a correlation between cab ride demand and FOMC during a certain time window. Then use **Poisson regression** to verify hypotheses, especially if your data involves count variables that follow a Poisson distribution. **Steps to follow**:
```
1.Model Specification: Formulate a Poisson regression model with your count data as the dependent variable and your predictor variables as the independent variables;
  
2.Fit the Model: Use statistical software (like R, Python's statsmodels, etc.) to fit the Poisson regression model to your data; 

3.Hypothesis Testing: Null Hypothesis (H0): Typically, the null hypothesis states that the coefficients of the predictors are equal to zero, meaning the predictors have no effect on the dependent variable. Alternative Hypothesis (H1): The alternative hypothesis states that at least one predictor coefficient is not equal to zero; 

4.Interpret the Coefficients: After fitting the model, examine the estimated coefficients and their standard errors. Most statistical software will provide a z-test for each coefficient, which you can use to determine if each coefficient is significantly different from zero; 

5.P-values and Significance: Check the p-values associated with the z-tests. If a p-value is below your chosen significance level (e.g., 0.05), you can reject the null hypothesis for that predictor. 
```
Here I use ride counts as dependent variable, FOMC flag, weekday, year and month as indicator.

## Summary
- Developed a Python workflow for collecting, cleaning, storing, and analyzing over 10GB of New York cab trip records
from 2010 to 2024, and created Tableau dashboards to visualize the data and support decision-making at higher levels.
- Conducted exploratory data analysis, including component decomposition, rate of change, sliding averages, and downsam-
pling; performed ADF stability testing and differential smoothing.
- Generated autocorrelation and partial autocorrelation plots, fine-tuned and compared multiple time series models, reduc-
ing the Akaike Information Criterion (AIC) by approximately 12%.
- Proposed and validated a hypothesis testing model for cab passenger flow using external data and Poisson regression,
establishing a significant correlation between passenger flow and commercial activities.
