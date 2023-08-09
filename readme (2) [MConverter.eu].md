**Predicting Weather Changes using ARIMA and SARIMA Time Series Model**

**Table of Contents:**

1.  **Requirements**

2.  **Dataset**

3.  **Data Preprocess**

4.  **Data Cleaning**

5.  **Exploring and Visualization:**

6.  **Approach One: ARIMA Model**

7.  **Approach Two: SARIMA Model**

8.  **Validation for both Models via Mean Squared Error (MSE)**

9.  **Final Results for both Models**

<!-- -->

1.  **Requirements:**

> · Python 3.5 or higher
>
> · Numpy
>
> · Pandas
>
> · Matplotlib
>
> · Statsmodels
>
> · Adfuller
>
> · Itertools
>
> · Warnings
>
> · datetime
>
> · Pmdarima
>
> · Auto_arima
>
> **In order to enable Pmdarima and for the code to run correctly,
> internet must be enabled in your Kaggle notebook:**
>
> Select the arrow on the bottom right hand corner of the notebook.
>
> <img src="media/image24.png" style="width:6.35938in;height:3.00383in"
> alt="Image" />
>
> Toggle internet settings to on.
>
> <img src="media/image19.png" style="width:2.26563in;height:4.2455in"
> alt="Image" />
>
> If the option to enable internet access is not available, there will
> be a link in its place allowing the user to verify their account with
> a phone number. The option should then be available.
>
> **The data set will have to be added in order for the code to run.**
>
> Click on ‘Add data’ in the right hand pane.

<img src="media/image23.png" style="width:6.5in;height:3.08333in" />

Click on the ‘+’ button next to the ‘Historic Hourly Weather Data’
dataset.

<img src="media/image26.png" style="width:6.5in;height:3.08333in" />

You should now see the dataset added under ‘Input’.

<img src="media/image25.png" style="width:6.5in;height:3.08333in" />

2.  **Dataset:**

[<u>https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=temperature.csv</u>](https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=temperature.csv)

3.  **Data Preprocess:**

Pre-processing began with excluding all non-US cities from the dataframe
and combining the rest into a single column for average hourly
temperature in the US by finding the mean. This was followed by
formatting the dates to remove the timestamp and then grouping all of
the hourly measurements into daily averages.

<img src="media/image10.png" style="width:6.5in;height:1.05556in" /><img src="media/image1.png" style="width:6.5in;height:0.72222in" />

4.  **Data Cleaning:**

In addition to having excluded non-US cities, the data cleaning involved
assigning points or ticks to better view the data without the context of
time and also converting the measurements from kelvin to Fahrenheit for
better interpretability.

<img src="media/image16.png" style="width:6.5in;height:0.44444in" /><img src="media/image5.png" style="width:6.5in;height:0.58333in" />

5.  **Exploring and Visualization:**

<!-- -->

1)  Plot to see all unique data points

> <img src="media/image8.png" style="width:4.35494in;height:3.55235in" />

2)  Perform Augmented Dickey-Fuller Test to determine if time series
    > data is stationary. Reject null hypothesis if p-value less than 5%

> <img src="media/image15.png" style="width:4.77428in;height:3.70313in" />
>
> <img src="media/image6.png" style="width:6.5in;height:5.13889in" />
>
> 2a) If data is not stationary, difference and perform another ADF test
> until p value is less than 5%
>
> <img src="media/image22.png" style="width:6.5in;height:5.91667in" />

**VI. Approach One: ARIMA Model**

1)  Perform AIC Test to acquire optimal ARIMA order

> <img src="media/image4.png" style="width:4.55032in;height:3.79193in" />

2)  Perform MSE on ARIMA Fitted Values against original differenced
    > dataset for validation

> <img src="media/image11.png" style="width:3.86979in;height:3.22082in" />

3)  Show daily prediction for one month after dataset

> <img src="media/image17.png" style="width:4.2412in;height:2.31771in" />

**VII. Approach Two: SARIMA Model**

1)  Plot differenced dataset and check for seasonality by performing
    > visual inspection on graph for seasonal pattern

> <img src="media/image13.png" style="width:4.82469in;height:3.10048in" />

2)  Perform AIC Test to acquire optimal SARIMA order

> <img src="media/image12.png" style="width:4.79688in;height:3.43622in" />

3)  Perform MSE on SARIMA Fitted Values against original differenced
    > dataset for validation

> <img src="media/image14.png" style="width:5.5609in;height:4.84336in" />

4)  Show daily prediction for one month after dataset

> <img src="media/image3.png" style="width:5.3357in;height:3.01398in" />

**VIII. Validation for both Models via Mean Squared Error (MSE):**

<img src="media/image21.png" style="width:4.71875in;height:3.24111in" />

<img src="media/image9.png" style="width:4.43229in;height:3.14664in" />

<img src="media/image7.png" style="width:4.63656in;height:3.33624in" />

**IX. Final Results for both Models:**

1)  Perform inverse operation on differenced dataset to revert data back
    > to its original scale in Fahrenheit

> <img src="media/image18.png" style="width:6.5in;height:8.18056in" />

2)  Plot Historical Data and Predictions

> <img src="media/image20.png" style="width:5.62432in;height:4.98438in" />
>
> <img src="media/image2.png" style="width:5.10938in;height:4.78541in" />
