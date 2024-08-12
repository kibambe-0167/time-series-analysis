# time-series-analysis
predictive analysis hons module assignment 2



# to do
- consider differencing before applying data to the model or apply log transformation
- linear regression of any features
- Exponential Moving Average (EMA): A weighted moving average that gives more weight to recent observations.
- Rolling Standard Deviation: Measures the variability of the time series over a rolling window, capturing changes in volatility.
- Lag Plot: A scatter plot of the time series against a lagged version of itself, used to identify patterns and relationships.
- Cross-Correlation: Measures the correlation between two time series at different lags, useful for identifying lead-lag relationships.
- Autoregressive (AR) Coefficients: Coefficients from fitting an autoregressive model, which captures the relationship between an observation and a number of lagged observations.
- CUSUM (Cumulative Sum Control Chart): Identifies shifts in the mean level of the time series.
- Bayesian Change Point Detection: Identifies structural changes in the time series using a probabilistic approach.






Testing the accuracy of an ARIMA (AutoRegressive Integrated Moving Average) model involves evaluating how well the model forecasts or predicts future values of a time series. Here are different methods to assess the accuracy of an ARIMA model:

### 1. **Residual Analysis**
   - **Residual Plots:** Analyze the residuals (the differences between observed and predicted values). Residuals should be randomly distributed (no patterns) and have a mean close to zero. 
   - **Ljung-Box Test:** A statistical test to check whether the residuals are independent and identically distributed. The null hypothesis is that the residuals are not autocorrelated. A significant p-value suggests that the model may not fully capture the time series' structure.

### 2. **Forecast Accuracy Metrics**
   - **Mean Absolute Error (MAE):** The average absolute difference between observed and predicted values. Lower values indicate better accuracy.
   - **Mean Squared Error (MSE):** The average squared difference between observed and predicted values. It penalizes larger errors more heavily.
   - **Root Mean Squared Error (RMSE):** The square root of MSE, providing error metrics in the same units as the original data.
   - **Mean Absolute Percentage Error (MAPE):** The average absolute percentage difference between observed and predicted values. It is scale-independent and provides a percentage-based error.
   - **Symmetric Mean Absolute Percentage Error (sMAPE):** A variation of MAPE that treats over- and under-predictions symmetrically.

### 3. **Out-of-Sample Testing (Cross-Validation)**
   - **Train-Test Split:** Split the time series into training and testing datasets. Fit the ARIMA model on the training set and test it on the testing set to evaluate its forecasting accuracy.
   - **Rolling Forecast Origin:** A method where the model is re-fitted after each new data point, and forecasts are made for the next point. The performance is averaged over multiple forecasts, giving a robust measure of accuracy.
   - **Time Series Cross-Validation:** Similar to k-fold cross-validation but adapted for time series. The data is split into multiple train-test sets, where each test set is a contiguous block of time.

### 4. **Comparison with Benchmark Models**
   - **Naïve Forecasting:** Compare the ARIMA model's performance with simple baseline models like the Naïve or Seasonal Naïve model, which assumes the next value is equal to the last observed value or the value observed in the last season, respectively.
   - **Exponential Smoothing (ETS):** Compare ARIMA forecasts with those from an ETS model to assess whether ARIMA provides significant improvements.

### 5. **Information Criteria**
   - **Akaike Information Criterion (AIC):** A metric that balances model fit and complexity. Lower AIC values indicate a better model. This criterion helps compare different ARIMA models with varying parameters.
   - **Bayesian Information Criterion (BIC):** Similar to AIC but with a stronger penalty for model complexity. It is useful when comparing models of different orders.

### 6. **Prediction Intervals**
   - **Coverage of Prediction Intervals:** Evaluate whether the observed values fall within the prediction intervals provided by the ARIMA model. The intervals should cover the true values with the expected frequency (e.g., 95% prediction intervals should cover the true values approximately 95% of the time).

### 7. **Diebold-Mariano Test**
   - **Diebold-Mariano Test:** A statistical test used to compare the accuracy of two forecasting models. It tests whether the difference in prediction errors between the models is statistically significant. 

### 8. **Visual Inspection**
   - **Plotting Forecasts:** Visually compare the forecasted values with actual values on a time series plot. Check for any consistent over- or under-predictions.
   - **Residual Q-Q Plot:** Check the normality of residuals by plotting them on a Q-Q plot. Deviations from the straight line indicate non-normality, which may suggest issues with the model.

### 9. **Outlier Detection**
   - **Check for Outliers in Residuals:** Outliers in residuals may indicate that the model is not capturing some aspects of the data correctly. Identifying and investigating these outliers can provide insights into model improvements.

By combining these methods, you can comprehensively assess the accuracy and reliability of an ARIMA model and refine it as needed to improve its forecasting performance.