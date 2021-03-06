# Python Forecasting Techniques Comparison

## Introduction

Performance comparison of various time series forecasting techniques, including deep learning methods, presented as Python implemenations in Jupyter notebooks. These notebooks are written so that they can be read and understood in isolation, and as such, there may be repetition in certain parts between them. The models presented in these notebooks have not been fully-optimised, and are intended to serve as a starting framework for anyone interested in implementing these forecasting techniques in their own projects.

This repository is actively being updated with more forecasting methods and datasets.

## Forecasting Techniques

The forecasting techniques demonstrated in this repository are as follows:
- [Average Method](Average) - A simple benchmark model<sup>1</sup>
- [(Seasonal) Naïve Method](Naive) - A simple benchmark model<sup>1</sup>
- [Linear Regression](LinearRegression)
- [ARIMA](ARIMA)<sup>2</sup>
- [ARIMAX](ARIMAX)<sup>2</sup>
- [SARIMA](SARIMA)<sup>2</sup>
- [SARIMAX](SARIMAX)<sup>2</sup>
- [Prophet](Prophet) - An open source time series forecasting method from Facebook<sup>3</sup>
- [SageMaker DeepAR](DeepAR) - A deep learning method on the AWS SageMaker platform<sup>4</sup>
- [Ludwig](Ludwig) (WIP) - A toolkit created by Uber on top of TensorFlow for training and testing deep learning models<sup>5</sup> 

## Datasets

Datasets that exhibit seasonality, and those that don't, are treated separately.

**Seasonal Datasets:**
- [California Solar Power](datasets/california-solar-power.ipynb) (CSP) - Power output of 405 photovoltaic power stations at five minute intervals<sup>6</sup>
- [Household Electricity Consumption](datasets/household-electricity-consumption.ipynb) (HEC) - Electricity consumption of 370 households in Portugal at 15 minute intervals<sup>7</sup>
- [Hourly Weather Temperature](datasets/hourly-weather.ipynb) (HWT) - Hourly temperatures for 36 US, Canadian and Israeli cities<sup>8</sup>
- [Hourly Weather Wind Speed](datasets/hourly-weather.ipynb) (HWS) - Hourly wind speeds for 36 US, Canadian and Israeli cities<sup>8</sup>
- [Hourly Weather Wind Directions](datasets/hourly-weather.ipynb) (HWS) - Hourly wind directions for 36 US, Canadian and Israeli cities<sup>8</sup>
- [San Francisco Traffic](datasets/san-francisco-traffic.ipynb) (SFT) - Hourly road occupancy rates for various San Francisco Bay Area freeways<sup>9</sup>

**Non-Seasonal Datasets:**
- [Daily Exchange Rates](datasets/daily-exchange-rates.ipynb) (DER) - Daily exchange rates between 1990 and 2016 of eight countries (Australia, Britain, Canada, Switzerland, China, Japan, New Zealand, Singapore)<sup>10</sup>

## Evaluation

For non-seasonal datasets, the *mean absolute scaled error* (MASE)<sup>11</sup> is used to evaluate and compare forecasting accuracies for the different techniques. For seasonal datasets, the seasonal variant (sMASE) is used.

## Results

The results are shown below and are also viewable in [this notebook](model-performance-comparisons.ipynb).

**Seasonal Datasets:**

||CSP|HEC|HWT|HWS|HWD|SFT|
|---|---|---|---|---|---|---|
|SARIMA|0.734733|1.60976|1.25492|0.806742|0.713394|1.06255|
|SARIMAX|0.75265|1.61433|1.3084|0.865172|0.731366|1.1555|
|Naive|1|1|1|1|1|1|
|DeepAR|1.0884|1.69218|1.92888|0.795072|0.754109|0.717766|
|Prophet|1.10443|1.63378|1.32722|0.849303|0.999691|1.4419|
|LinearRegression|1.46422|2.03795|1.15451|0.821911|0.830871|1.51436|
|ARIMA|3.14786|2.04262|1.18837|0.794829|0.838663|1.26169|
|ARIMAX|3.62378|2.01298|1.4158|0.889121|0.875279|1.40512|
|Average|5.20921|2.39973|2.11568|0.813868|0.878027|1.95147|


**Non-Seasonal Datasets:**

||DER|
|---|---|
|Naive|5.42765|
|DeepAR|5.7467|
|ARIMA|6.1503|
|Average|16.7777|

---
#### References:<br>
1: [Forecasting: Principles and Practice](https://otexts.org/fpp2/simple-methods.html)<br>
2: [Autoregressive integrated moving average (Wikipedia)](https://en.wikipedia.org/wiki/Autoregressive_integrated_moving_average)<br>
3: [facebook prophet](https://github.com/facebook/prophet)<br>
4: [Amazon SageMaker DeepAR Forecasting](https://docs.aws.amazon.com/sagemaker/latest/dg/deepar.html)<br>
5: [Uber Ludwig](https://github.com/uber/ludwig/)<br>
6: [National Renewable Energy Laboratory](https://www.nrel.gov/grid/solar-power-data.html)<br>
7: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014)<br>
8: [Kaggle](https://www.kaggle.com/selfishgene/historical-hourly-weather-data/home)<br>
9: [Caltrans PeMS](http://pems.dot.ca.gov)<br>
10: [GitHub/laiguokun](https://github.com/laiguokun/multivariate-time-series-data/tree/master/exchange_rate)<br>
11: [Forecasting: Principles and Practice - Chapter 3.4](https://otexts.org/fpp2/accuracy.html)<br>
