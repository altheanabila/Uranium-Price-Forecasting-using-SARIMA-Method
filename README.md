# Uranium-Price-Forecasting-using-SARIMA-Method

This time I would like to run an Uranium Price Forecasting using SARIMA Method. The process began through ARIMA method using decomposition and differencing at first, and then using SARIMA line of code at the end.
The data is downloaded from yahoo finance from Uranium ETF from August 2016 - July 2021.

1. import related libraries

![textimage1](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%201.png)


2. convert the data into panda dataframes


![textimage2](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%202.png)


3. We use date as index



![textimage3](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%203.png)


4. Fulfill missing value with mean



![textimage4](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%204.png)



5. We run the decomposing time series model both additive and multiplicative in order to remove trend and seasonality. However, the trend and seasonality still exist.


![textimage5](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%205.png)



![textimage6](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%206.png)



6. Then we use python code in order to do differencing for lag1, but there's still trend and seasonality problem



![textimage7](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%207.png)


![textimage8](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%208.png)



7. We use second lag differencing

![textimage9](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%209.png)


8. Plot the data. As we can see that the trend and seasonality have been removed.

![textimage10](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2010.png)

![textimage11](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2011.png)



9. Plotting Autocorrelation plot in order to find the value of p. We got p value at 2


![textimage12](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2012.png)


10. Plotting PACF to find out the value of q. We got value at 2


![textimage13](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2013.png)



11. run ARIMA code with order (2,1,2)

`from statsmodels.tsa.arima_model import ARIMA`

`model = ARIMA(df['Adj Close'], order= (2,1,2))`



12. Display model result


![textimage14](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2014.png)


13. Plot the residuals


![textimage15](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2015.png)



14. display the output forecast


![textimage16](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2016.png)


15. Run SARIMAX with the same order of p,d,q in ARIMA and seasonal order P,D,Q,S (1,1,1,12). 12 because of monthly data


![textimage17](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2017.png)


16. Plot the residuals


![textimage18](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2018.png)


17. Forecast the model


![textimage19](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2019.png)


18. Visualize the predicted value and forecasted value


![textimage20](https://github.com/altheanabila/Uranium-Price-Forecasting-using-SARIMA-Method/blob/main/pic%2020.png)
