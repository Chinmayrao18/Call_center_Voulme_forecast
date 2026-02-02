# Call_center_Voulme_forecast
Project Overview: The goal of this project was to forecast monthly incoming calls using historical data from the organization. Multiple time series forecasting methods were implemented and evaluated to identify the model that best captures the short-term call volume patterns.


**Methods Implemented:**

1)Moving Average (SMA)
A simple 3-month moving average was calculated to smooth out short-term fluctuations.
RMSE: 1048
This method performed the best on the Jan–Jun 2024 test period due to the series being relatively stable with minor month-to-month variations. The moving average effectively captures the central tendency of the calls, while more complex models overfit the small dataset.

2)ARIMA
Auto-Regressive Integrated Moving Average (ARIMA) model was implemented to capture trend and autocorrelation.
RMSE: 2462
ARIMA overestimated fluctuations due to the short evaluation period.

3)SARIMA
Seasonal ARIMA was used to model trend and seasonality explicitly.
RMSE: 2267
While accounting for seasonality, the model slightly overfit the minor variations, leading to higher RMSE than moving average.

4)Prophet
Facebook’s Prophet model was applied to capture trend and yearly seasonality.
RMSE: 4955
Prophet over-predicted due to the very short forecast horizon and minimal seasonality in this subset of the data.

**Machine Learning Approaches (Optional)**
Models like Random Forest and XGBoost can be used with lag features and rolling statistics as predictors.
These require feature engineering to convert the time series into a supervised learning format.
Key Insights:

Moving Average Outperforms Others:
The 3-month simple moving average had the lowest RMSE. This is because the incoming calls series during the forecast period (Jan–Jun 2024) was relatively stable, and short-term averages provided the best estimate.

Complex Models Not Always Better:
More sophisticated models like ARIMA, SARIMA, and Prophet overfit the small dataset and short forecast horizon, resulting in higher RMSE.

Visualization:
For each method, a graphical comparison of forecast vs actual calls was created. This visual representation clearly shows how closely each model tracks the actual calls, highlighting why the moving average performs best for this specific period.
