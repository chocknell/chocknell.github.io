---
layout: post
title: New York Taxi Anomaly Detection
---

Time Series Analysis of New York Taxi usage data to evaluate potential anomalies within the given time period

### Time Series Analysis
Having a desire to dig deeper into Time Series data, I found a dataset on  [Kaggle](https://www.kaggle.com/datasets/julienjta/nyc-taxi-traffic) which was ideal to look more into the various theoretical elements behind this type of analysis, as well as allowing for further learning and investigation into anomaly detection. 

Taking an initial look into this data, the plot below shows that there are a number of potential areas to look into - the first being that the data as it is is not stationary.

*NYC Taxi Usage*
![original]({{ site.baseurl }}/images/taxi/original.png)

The data being shown above has been collected in half hour intervals between the months of July 2014 and February 2015.

### Stationary Data
Data is considered to be stationary when the variance is equal across a constant mean throughout the duration of the time being assessed with no sign of seasonality. It is clear from the above image that although the mean seems to be fairly constant, the variance differs greatly and there are obvious indications of seasonality. To look into rectifying this, a number of **differencing** activities have been carried out to look specifically into how the data changes over a number of defined time periods. In this case, we are looking into hours, days and weeks. Below is the image of the data with weekly differencing (i.e. the difference from the previous week) which shows no sign of seasonality and fairly equal variance, indicating this as being close to stationary.

*NYC Taxi Usage with Weekly Differencing*
![weekly_difference]({{ site.baseurl }}/images/taxi/weekly_difference.png)

### Seasonal Decomposition
Using the knowledge learnt above, the time series data can then be **decomposed** to evaluate the trend, seasonality and residuals when taking each *season* in this case to be a week.

*NYC Taxi Usage with Weekly Seasonal Decomposition*
![weekly_seasonality]({{ site.baseurl }}/images/taxi/weekly_decomposition.png)

Already looking at the above breakdown of the data, there seem to be some obvious locations of potential anomalies seen within the residual plot. The plot also shows that there is no obvious trend within the data, with there being a variety of peaks and troughs occuring throughout the given time period.

### Anomaly Detection

There are number of different ways to detect anomalies within data, with this project initially looking into **Median Absolute Deviation (MAD)**, which is a measure of dispersion about the median, making it resilient to outliers. When assessing time series anomalies using MAD, the classifier is applied to the *residuals* of the decomposed data, as these don't take into account any seasonality. The plot below has the outcome of the MAD classifier highlighted in red in respect to the real decomposed residuals in blue (with weekly seasonal decomposition).

*Median Absolute Deviation Anomaly Detection*
![weekly_MAD]({{ site.baseurl }}/images/taxi/weekly_MAD.png)

The above graphs shows that the MAD classifier has highlighted **eight** key time periods which could be classified as an outlier. 

Before digging further into these specific dates and their potential meaning, a second form of classifier is assessed - namely **iForest** (or Isolation Forest), which is a form of unsupervised decision tree classifier specifically used for anomaly detection. An iForest classifier is fit on a complete dataset (not just the residuals), so in order to allow for stationary data, the taxi usage with weekly differencing is used. A second column depicting the day of the week is also added, to ensure that this is factored in to the assessment. With optimization of the hyperparameters, the following plot of the anomalies alongside the weekly differenced data is shown below.

*iForest Anomaly Detection*
![weekly_MAD]({{ site.baseurl }}/images/taxi/weekly_iforest.png)

Due to the weekly differencing that has been applied for stationarity, the anomalies highlighted above are showing clear gaps of 7 days between the highlights max/min values. Looking into these in more detail, there seem to be **seven** clear dates to look into in more detail. This is done in the table below, which also indicates which of the dates is an anomaly, as well as the event that happened on this date which may have led to this.

| Outlier Dates                | Key Date      | Occasion                     |
| :--------------------------: | :-----------: | :--------------------------: |
| 11th - 13th July             | 4th July      | Independence Day             |
| 1st & 8th September          | 1st September | Labor Day                    |
| 2nd & 9th November           | 2nd November  | New York Marathon            |
| 28th November & 4th December | 28th November | Thanksgiving                 |
| 25th December & 1st January  | 25th December | Christmas                    |
| 1st & 8th January            | 1st January   | New Years Day                |
| 19th & 26th January          | 26th January  | 2015 North American Blizzard |

These dates also align with the anomalies found using the MAD method, with the exception of the 19th January.

### Conclusions
For an initial investigation into possible anomalies of time series data, two methods have been used that were able to accurately predict seven specific times where the taxi usage in New York City was abnormal. Unsurprisingly, these occurred during a number of National holidays (i.e. Independence Day, Christmas and New Year), however also highlighted a couple of more unexpected events that impacted the use of taxis - namely the New York Marathon in November 2014 and a large snow storm in January 2015.
