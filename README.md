# Investigating NYC EMS Calls with Time Series Analysis

#### Data Selection 

Gathered data surrounding ~7 million EMS calls form 2013-2017 from NYC Open Data. Aimed to answer the following questions: 

    -Can we predict the time elapsed between an EMS call and an ambulance's arrival time in order to provide callers with more      accurate ETAs? 
    -Can we forecast the volume of EMS calls to ensure ambulance forces are adequately prepared? 

#### Analysis Approach 

    -Integrated EMS call data with daily weather data and holiday data 
    -Resampled data to weekly sums and averages
    -Accounted for AR, MA, difference, and seasonal terms
    -Trained SARIMAX model on first 80% of data
    -Predicted weekly response times and call volume for 2017
    -Measured RMSE and improvement over baseline model 
    
#### Predicting Weekly Call Volume 

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_call_volume.png)

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_call_volume_facebook.png)

#### Predicting Weekly Average Response Time 

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_average_time.png)

![](https://github.com/kahartman2/nyc_911_calls/blob/master/weekly_average_time_facebook.png)
