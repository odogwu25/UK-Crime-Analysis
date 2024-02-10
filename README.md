# UK CRIME ANALYSIS

Using time series data, this analysis will look at the trend of violent crimes using data provided by the UK police department and determine whether there are other causes of gun-related crimes besides the traditional gang culture and the locations with more gun-related crimes. My jupyter notebook also has a detailed comment on each cell and markdowns for more explanation. 

## The Technical Approach Used Will Entail The Following;

1. Hosting the data on Azure blob storage to speed up computational time.
2. Utilising Apache Spark for handling large volumes of data.
3. Filtering the data sets to get only relevant information.
4. Visualizing outcomes in a very clear and understandable format.
5. Using statistical and machine learning techniques to ascertain facts and make possible predictions.
   

# KEY FINDINGS

**1. Violent Crimes have risen steadily over the years. This can be seen in the charts below.** 

![](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/violent_Time%20serioes.png)

![](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/stack%20plot.png)

![The candle stick shows the retracement each year](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/Barplot_candle.png)


**2. There's a positive correlation between firearm and drug crimes. This can be seen in the scatter plot and heatmap below. The correlation coefficient of 0.84 depicts a strong relationship**

![](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/drug%20%26%20firearm%20corr.png)

![](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/drug%20and%20firearm%20scatterplot.png)


# ACHIEVING STATIONARITY

To eliminate any visible correlation and collinearity with the historical data, time series data must be made stable. The features or value of a sample observation in stationary time-series data are independent of the timestamp at which it is observed. For instance, a hypothetical dataset of an area's population broken down by year would be non-stationary if it showed that the population doubled every year or increased by a fixed amount. Every observation is strongly influenced by the year because the population value depends on how far away it is from a chosen former year.

![](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/detrending.png)


# FUTURE PREDICTION USING ARIMA

The autoregressive integrated moving average(ARIMA) was used for prediction. Before that, the data used for this model had been made stationary. This model was adopted because it is best used to understand previous data while predicting future outcomes. This method assesses the significance of historical variations, considers broad trends, and reduces the impact of outliers or brief aberrant changes in the data. ARIMA incorporates these ideas in its combined autoregressive and moving-average approach to model stationary time-series data. The historical trends, seasonality, unpredictability, and other non-static phenomena that people miss are all perfectly captured by ARIMA.

![](https://github.com/odogwu25/UK-Crime-Analysis/blob/main/crimeimages/Arima.png)

# CONCLUSION

Several interactive queries and counts from the publicly available data set were done using Apache Spark SQL to evaluate these assertions. From 2010 to June 2021, it was seen that violent crimes—later classified as sexual offences were progressively on the rise. The trend may have been stagnant between 2019 and 2020 due to the pandemic, but a modest regression that appeared to indicate a change in direction was observed in the final months of 2021. It was also discovered that Birmingham does not appear among the top 10 cities when grouped by decreasing order in the data frame that contained all firearm occurrences per head in each city, refuting the second claim that Birmingham had the highest number of firearm events per head. Lastly, The Pearson correlation coefficients were used to investigate and assess the hypothesis that drug use was linked to firearm occurrences. The positive outcome provided both coefficient values of 1.0 and 0.84, indicating a high correlation.
