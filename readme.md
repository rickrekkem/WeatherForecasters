**Predicting Weather Changes using ARIMA and SARIMA Time Series Model**

**Table of Contents:**

I.  **Requirements**

II. **Dataset**

III. **Data Preprocess**

IV. **Data Cleaning**

V.  **Exploring and Visualization:**

VI. **Approach One: ARIMA Model**

VII. **Approach Two: SARIMA Model**

VIII. **Validation for both Models via Mean Squared Error (MSE)**

IX. **Final Results for both Models**

I.  **Requirements:**

> 	• Python 3.5 or higher
>
> 	• Numpy
>
> 	• Pandas
>
> 	• Matplotlib
>
> 	• Statsmodels
>
> 	• Adfuller
>
> 	• Itertools
>
> 	• Warnings
>
> 	• datetime
>
> 	• Pmdarima
>
> 	• Auto_arima
>
> **In order to enable Pmdarima and for the code to run correctly,
> internet must be enabled in your Kaggle notebook:**
>
> Select the arrow on the bottom right hand corner of the notebook.
>
> ![Image](readme/media/image24.png)
>
> Toggle internet settings to on.
>
> ![Image](readme/media/image19.png)
>
> If the option to enable internet access is not available, there will
> be a link in its place allowing the user to verify their account with
> a phone number. The option should then be available.
>
> **The data set will have to be added in order for the code to run.**
>
> Click on 'Add data' in the right hand pane.

![](readme/media/image23.png)

Click on the '+' button next to the 'Historic Hourly Weather Data'
dataset.

![](readme/media/image26.png)

You should now see the dataset added under 'Input'.

![](readme/media/image25.png)
II. **Dataset:**

[[https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=temperature.csv]{.underline}](https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=temperature.csv)

III. **Data Preprocess:**

Pre-processing began with excluding all non-US cities from the dataframe
and combining the rest into a single column for average hourly
temperature in the US by finding the mean. This was followed by
formatting the dates to remove the timestamp and then grouping all of
the hourly measurements into daily averages.

![](readme/media/image10.png)
![](readme/media/image1.png)

IV. **Data Cleaning:**

In addition to having excluded non-US cities, the data cleaning involved
assigning points or ticks to better view the data without the context of
time and also converting the measurements from kelvin to Fahrenheit for
better interpretability.

![](readme/media/image16.png)
![](readme/media/image5.png)

V.  **Exploring and Visualization:**

1)  Plot to see all unique data points

> ![](readme/media/image8.png)

2)  Perform Augmented Dickey-Fuller Test to determine if time series
    > data is stationary. Reject null hypothesis if p-value less than 5%

> ![](readme/media/image15.png)
>
> ![](readme/media/image6.png)
>
> 2a) If data is not stationary, difference and perform another ADF test
> until p value is less than 5%
>
> ![](readme/media/image22.png)

**VI. Approach One: ARIMA Model**

1)  Perform AIC Test to acquire optimal ARIMA order

> ![](readme/media/image4.png)

2)  Perform MSE on ARIMA Fitted Values against original differenced
    > dataset for validation

> ![](readme/media/image11.png)

3)  Show daily prediction for one month after dataset

> ![](readme/media/image17.png)

**VII. Approach Two: SARIMA Model**

1)  Plot differenced dataset and check for seasonality by performing
    > visual inspection on graph for seasonal pattern

> ![](readme/media/image13.png)

2)  Perform AIC Test to acquire optimal SARIMA order

> ![](readme/media/image12.png)

3)  Perform MSE on SARIMA Fitted Values against original differenced
    > dataset for validation

> ![](readme/media/image14.png)
4)  Show daily prediction for one month after dataset

> ![](readme/media/image3.png)

**VIII. Validation for both Models via Mean Squared Error (MSE):**

![](readme/media/image21.png)
![](readme/media/image9.png)

![](readme/media/image7.png)

**IX. Final Results for both Models:**

1)  Perform inverse operation on differenced dataset to revert data back
    > to its original scale in Fahrenheit

> ![](readme/media/image18.png)
2)  Plot Historical Data and Predictions

> ![](readme/media/image20.png)
>
> ![](readme/media/image2.png)

![image](https://github.com/rickrekkem/WeatherForecasters/assets/109248041/c8970d5c-6c99-40b5-8ee8-6d233c6509fb)
