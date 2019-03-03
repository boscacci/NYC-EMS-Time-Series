# Investigating NYC EMS Calls with Time Series Analysis

A time series analysis of medical emergency Call Volumes and Response Times in the five boroughs.

[Kayla Hartman](https://github.com/kahartman2/) and I were curious about **Time Series** analysis and modeling: Using temporal lags of a dependent variable as predictors of that same variable, in tandem with **other exogenous variables**, to infer values into the future, and validating those predictions.

Some openly available data pertaining to ambulance call volumes and response durations, we thought, might be a good candidate for this sort of investigation and experimentation. The real-world applications are pressing and easily explained: It'd be good to be able to approximate how many ambulances ought to be on the road at any given time, and it'd be nice to be able to guess how long it will take for the ambulance to reach an ailing denizen.

### The Data 

NYC open data has a [repository with roughly 7 million EMS calls from 2013-2017.](https://data.cityofnewyork.us/Public-Safety/EMS-Incident-Dispatch-Data/76xm-jjuj) We dropped a good number of columns just for computational maneuverability but did go ahead and use all rows.

### Approach 
Our steps were as follows:

    -Integrate EMS call data with daily weather data and holiday data 

    -Resample data to weekly sums and averages

    -Account for AR, MA, difference, and seasonal terms

    -Train SARIMAX model on first 80% of data

    -Predict weekly response times and call volume for remaining 20%

    -Measure RMSE and compare with dummy baseline model

    -Adjust SARIMAX terms and repeat
    
    -Compare our custom model with facebook's "prophet" forecaster
    
### Predicting Weekly Call Volume 

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_call_volume.png)

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_call_volume_facebook.png)

### Predicting Weekly Average Response Time 

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_average_time.png)

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_average_time_facebook.png)
