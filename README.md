# Cryptocurrency-Trend-Forecast
ARIMA Model

Use history bitcoin price from 2012 to 2018 to forcast bitcoin price from at the end of 2018 to 2019 (8 months)

During the preparation phase, we need to first explore the data and visualize Bitcoin's historical trends. Data can be aggregated by different time scales (day, month, quarter, year) for visualization. Among these, we choose the monthly scale for forecasting, focusing on the 'Weighted_Price' field, which represents the daily average price of Bitcoin. When aggregated monthly, 'Weighted_Price' reflects the average price for that month.

In the prediction phase, we create an ARIMA time series model. Since we do not know the optimal values for `p` and `q`, we set a range for them, such as `range(0,3)`, and calculate the AIC values for different models. We then select the ARIMA model with the smallest AIC value. Finally, we use this optimal ARIMA model to forecast the average price trend of Bitcoin for the next 8 months and visualize the results.

I created all possible combinations of `(p, q)` within the range(0,3) using the `product` function and calculated the AIC values for each ARIMA(p,q) model, saving the parameters of the model with the lowest AIC value. I then used this model to forecast Bitcoin's price for the next 8 months. The results show that, in the 8 months following October 2018, Bitcoin's price would drop to around $4000, which indeed happened as it fell to $4000 or even lower during that period. We chose the monthly time scale, reducing the data dimensionality and saving time on ARIMA model training. The graph of Bitcoin prices (in dollars), divided by month, shows a trend similar to the daily data, reducing local volatility while still reflecting the overall trend, thus saving on ARIMA model training time.
