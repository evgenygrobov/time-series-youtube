# Forecast new YouTube  trending video release  with Arima and Time Series

>Objectives of the project:
* define seasonal components 
* achive stationarity
* predict dynamic of new trending video release on YouTube

Before I dive into any statistical methods for predicting future data, let's take a look at the data we already have.

**We may see daily dynamic of new video releases in first quartile of 2018**
![image of count releases daily](https://github.com/evgenygrobov/time-series-youtube/blob/main/images/video_release_dayly.png)

From here I can pick out an immediate trends

![count of video release by hour](https://github.com/evgenygrobov/time-series-youtube/blob/main/images/release_hourly.png)

It looks like there could ve some structers behaviour in the weeks themselves, some signal from the day of week.

**Here we can see a few different weeks.

![signal weekly](https://github.com/evgenygrobov/time-series-youtube/blob/main/images/signal_weekly.png)

It seems there is a pattern in hourly video releases within a week: new video publushing more likely in the middle of the week

If this assumption is true I could see a strong seasonal component to the data. 
**Here we can see Tue, Wed, Thur, Fr are highlighted**
![daily release workday highlighted]()

## Here I determine if the data is stationary
![image of stationarity](https://github.com/evgenygrobov/time-series-youtube/blob/main/images/stationarity_7periods.png)

The most striking feature here is the oscillatory nature of the autocorrelation plot. This is clear indication of non-stationarity. 

Lets apply differencing that should result in a stationary series.

![image of good autocorrelation](https://github.com/evgenygrobov/time-series-youtube/blob/main/images/good_autocorr.png)

This looks possibly more stationary.
Lets run hypothesis test to be more confident

```
ADF p-value: 0.00
```

**Ok, there is a time to make a predictions for the next four weeks**

![weekly forecast](https://github.com/evgenygrobov/time-series-youtube/blob/main/images/weekly_forecast.png)

The prediction for the next four week is clear, there should be a downtrend in numbers of new video release. And it is. You may check youself.

## Conclusion.
- We defined seasinal components, such as weekly releases of new video. The videos publishing within the work day mostly.
- We achived stationarity by applying differenciation.
- Prediction was made. I am  betting it is correct.
