# Investigating NYC EMS Calls with Time Series Analysis

A time series analysis of medical emergency Call Volumes and Response Times in the five boroughs.

![](response_times_forecast.png "Predicted vs Actual EMS Response Times")

[Kayla Hartman](https://github.com/kahartman2/) and I were curious about **Time Series** analysis and modeling: Using temporal lags of a dependent variable as predictors of that same variable, in tandem with **other exogenous variables**, to infer values into the future, and validating those predictions.

### The Data 

NYC open data has a [repository with roughly 7 million EMS calls from 2013-2017.](https://data.cityofnewyork.us/Public-Safety/EMS-Incident-Dispatch-Data/76xm-jjuj) We dropped a good number of columns just for computational maneuverability but we did go ahead and use all rows.

### The Question

How well can we forecast the **total number (or "volume") of EMS calls** in future weeks? 

How well can we forecast the **average ambulance response time** in future weeks?

### Approach 
Our steps were as follows:

    -Integrate EMS call data with daily weather data and holiday data 

    -Resample the (occurrence-based) data to (temporally evenly spaced-out) sums and averages

    -Account for AR, MA, difference, and seasonal terms

    -Train SARIMAX models on the first 80% of the data

    -Predict weekly response times and call volume for the remaining 20%

    -Measure RMSE and compare with cost from dummy baseline model

    -Adjust SARIMAX terms and repeat

    -Compare our custom model's cost with facebook "prophet" forecaster's
    
