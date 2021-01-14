---
layout: post
title:      "Working with Time Series Data"
date:       2021-01-14 00:43:31 +0000
permalink:  working_with_time_series_data
---


Hello readers! I have finally arrived at the Module 4 Project. It's very exciting to know that I'm so close to completing the course! This project was probably my favorite so far since I got to work with time series data. We were able to select from time series modeling, recommendation systems, image classification, or NPL. I chose time series modeling since it will probably be the most useful to me in my career. I hope to continue working in the public health field or in environmental science and both fields frequently use time series data. 

For the time series project, we were given a dataset from Zillow that contained the housing sale values for zip codes across the United States. I filtered the data to only include zip codes from Austin, TX. The goal was to select the 5 best zip codes in Austin to invest in. 

I started by changing the date time format to fit the model later on. Then I had to change the format of the dataset from long to wide. Luckily, code for both of these tasks were included in the notebook for the project. 

```
def get_datetimes(df):
    return pd.to_datetime(df.columns.values[7:], format='%Y-%m')
```

```

def melt_data(df):
    melted = pd.melt(df, id_vars=['RegionID','RegionName', 'City', 'State', 'Metro',
                                  'CountyName', 'SizeRank'], var_name='time')
    melted['time'] = pd.to_datetime(melted['time'], infer_datetime_format=True)
    melted = melted.dropna(subset=['value'])
    return melted.groupby('time').aggregate({'value':'mean'})
```

Now it was time to start building a model. Once again my excellent instructor helped me out by sending the following [article](http://machinelearningmastery.com/grid-search-arima-hyperparameters-with-python/).

For the time series model I used, ARIMA, you need 3 hyperparameters. The autoregressive value (AR), a differencing parameter (I), and the moving average parameter (MA). The code included in the article offers a way to grid search for the hyperparameters. It selects the best parameters for your model based on the mean squared errors (MSE). The order of parameters with the least MSE is selected as the best. 

After I got the best parameters for ARIMA, I built the model and visualized it the zip code's housing sale values and the forecasted values. I chose to forecast 3 years after the end of the data so 2021. 

I then repeated these steps of grid searching and building the model for every zip code in Austin. The code for the grid search took the longest - about 20 minutes per zip code. Luckily I had time and was able to do other things while I waited for the code to run. 

After all of the predicted sale values were determined, I selected the top five in the city. One was located in North Austin where a new shopping center was built and where the construction of the new soccer stadium has begun. The best zip code had an 11.32% projected rate of return on investment. The average for all of the zip codes in Austin was approximately 7%. 

I was able to learn so much about how to create a predicative model with time series data and I am excited to work with it again in the future. 



