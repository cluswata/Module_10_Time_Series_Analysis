# Module_10_Time_Series_Analysis
Comparing the Seasonal Decomposition of sunspots activity data and air passenger data


The seasonal_decompose function with an additive model was used to decompose the time series into trend, seasonal, and residual components.
Plotting Components: We created a 4x1 subplot layout to visualize the observed data, trend, seasonal component, and residuals respectively.
•	Observed: The original time series; sunspot counts (SUNACTIVITY) and number of passengers (#Passengers) respectively. 
•	Trend: The estimated trend component of the time series.
•	Seasonal: The seasonal component showing the repetitive pattern over time. A vertical line to indicate the lowest point of each year was added.
•	Residual: The residual component after removing trend and seasonal effects, representing irregular fluctuations in the data. A horizontal line is added to aid in visualizing where the residuals center around.
Tests:
•	Autocorrelation:  Correlation of a time series with a lagged version of itself, measures how each observation in a time series is related to its past observations.
o	Durbin - Watson Statistic: Tests for autocorrelation in the residuals of a regression or time series model. It ranges from 0 to 4, where a value near 2 indicates no autocorrelation and Values significantly different from 2 indicate the presence of autocorrelation.

•	Stationarity: A crucial assumption for many time series models, as it ensures that the statistical properties of the series do not change over time. 
o	Significant spikes in Autocorrelation Plot for Residuals at various lags suggests that there may still be patterns in the residuals that are not captured by the trend and seasonal components hence non-stationarity.
o	Augmented Dickey-Fuller (ADF) test: Used to determine whether a time series is stationary or not. If the test statistic is less than the critical value from the ADF distribution, we reject the null hypothesis (suggesting stationarity). However, if the test statistic is greater than the critical value, we fail to reject the null hypothesis (indicating non-stationarity).
Transformations: Difference from the first value was derived for SUNACTIVITY. Both datasets were split into history (tdata) and future (fdata) sets at their 75th percentile value (ratio 75:25).


Interpretation: 
Sunspot activity: No trend and no seasonality observed in the data.

Airline Passengers: There is a visible and significant up-trend as well as seasonality in the data. 
Autocorrelation: Positive value of the Durbin – Watson test indicates positive autocorrelation present suggesting that past values may influence future values in a positive manner. 
Stationarity: Significant spikes were observed in the autocorrelation plot of residuals at various lags suggest that there may still be patterns in the residuals that are not captured by the trend and seasonal components hence non-stationarity. This confirmed by the Augmented Dickey-Fuller (ADF) test for stationarity (statistic = -0.77; p-value = 0.82 > 0.05).
