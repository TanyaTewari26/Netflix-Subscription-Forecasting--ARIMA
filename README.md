# Netflix-Subscription-Forecasting--ARIMA
Netflix Subscriptions Forecasting using ARIMA in Python
Using techniques like time series forecasting, Netflix can predict the expected number of new subscribers in a given time period and understand the growth potential of their business. Below is the process we can follow to forecast subscription counts for Netflix:

1. Gather historical Netflix subscriptions growth data
2. Preprocess and clean the data
3. Explore and analyze time series patterns
4. Choose a time series forecasting model (e.g., ARIMA, LSTM)
5. Train the model using the training data
6. Forecast future Netflix subscription counts

So the process for forecasting subscriptions for Netflix starts with collecting a dataset based on the historical growth of Netflix Subscribers. Dataset consists of Netflix subscriptions till Q3-2023.

Based on the dataset, plotting the quarterly subscription growth of Netflix
![png](./Plot1.png)

Since the Netflix subscribers growth is not seasonal, we can leverage forecasting technique like ARIMA in this dataset.

We calculate the quarterly growth rate using bar graph and plot quarterly subscription growth rate
![png](./Plot2.png)

Now, we calculate the yearly subsciption growth rate using bar graphs

![png](./Plot3.png)

Now we find the value of p and q by plotting the ACF and PACF of differenced time series

![png](./Plot5.png)

Here we first calculated the differenced time series from the original time_series, removed any NaN values resulting from the differencing, and then plotted the ACF and PACF to provide insights into the potential order of the AR and MA components in the time series. These plots are useful for determining the appropriate parameters when using the ARIMA model for time series forecasting.

Based on the plots, we find that p=1 and q=1. The ACF plot cuts off at lag 1, indicating q=1, and the PACF plot also cuts off at lag 1, indicating p=1. As there is a linear trend in the subscription growth rate, we can set the value of d as 1 to remove the linear trend, making the time series stationary.

And implement the ARIMA model in our dataset-

Visualizing the results of Netflix Subscriptions Forecasting for the next five quarters:

![png](./Plot4.png)
