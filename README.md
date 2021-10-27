# ML_Forecasting
Time series and regression analysis for Yen Futures.

# A Yen for the Future

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\Future Yen.png)



# Background

____

As the financial departments of large companies often deal with foreign currency transactions while doing international business, they are always looking for anything that can help them better understand the future direction and risk of various currencies. Hedge funds, too, are keenly interested in anything that will give them a consistent edge in predicting currency movements.

In this project, time series forecasting and linear regression models are used to forecast the value of the Japanese Yen vs. the US Dollar.

# Return Forecasting: Initial Time-Series Plotting

____

Historical Yen-Dollar futures contract data is loaded onto the Jupyter Notebook. 'Settle' prices are plotted to note any short and long term patterns.

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\Yen Futures Settle Prices.png)

- In the short term, the Japanese Yen vs US Dollar is quite volatile. 
- In the long term, the Yen has put in consistent higher lows and has ultimately gained value against the Dollar over the past 3 decades.

# Decomposition Using a Hodrick-Prescott Filter

____

A Hodrick-Prescott Filter is applied to decompose the 'Settle' price into a trend and noise. Below the 'Settle' price is plotted alongside the 'Trend' in the first image, and the second image shows a plot of the 'Noise'.

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\Settle vs Trend.png)

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\Settle Noise.png)



# Forecasting Returns using an ARMA Model

An ARMA model is used to forecast returns - however the model is not a good fit as the P values are all well above the 0.05 threshold.

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\ARMA 5 Day Forecast.png)

# Forecasting the Settle Price using an ARIMA Model

An ARIMA model is used to forecast the 'Settle Price' - however the model is not a good fit as the P values are also all well above the 0.05 threshold.

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\ARIMA 5 Day Forecast.png)

# Volatility Forecasting with GARCH

Rather than predicting returns, a GARCH model is used to forecast near-term volatility of Japanese Yen futures returns. Being able to accurately predict volatility is very useful in trading of derivatives, and/or to quantify maximum losses. This is a good model to utilize as the P values conform to our standard of below 0.05.

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\GARCH 5 Day Forecast.png)

# Conclusions

- Based on this time series analysis, I would be inclined to buy Yen now. As the saying goes: The trend is your friend!
- The risk of the Yen is expected to increase as time goes on.
- I would feel confident on using the GARCH model out of the three as it has by far the best P value.

# Linear Regression Forecasting

Using the SKLearn linear regression model to predict Yen futures ("settle") returns with *lagged* Yen futures returns. Here we note the 'out-of-sample' data has a lower RMSE, however the plots show the Settle price is actually higher than predicted.

![](C:\Users\chemi\Desktop\ASU Fintech Bootcamp\Machine Learning HW\images\Linear Regression Model.png)
