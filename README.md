# BikeDemandAnalysis
A comprehensive analysis of bike demand using linear regression techniques. 

## Table of Contents
* General Info
* Key Findings
* Model performance
* Recommendations
* Technologies Used
* Contacts

## General Information
BoomBikes, a US bike-sharing provider, faces revenue challenges due to the COVID-19 pandemic and seeks to analyze bike-sharing demand patterns for post-pandemic recovery. The company aims to identify key factors influencing bike rental demand to optimize their business strategy and gain competitive advantage. The goal is to build a predictive model that:
* Which variables are significant in predicting the demand for shared bikes.
* How well those variables describe the bike demands

## Key Findings
* Dataset: 730 rows, 16 columns, no missing values.
* Target Variable: 'cnt' is the total bike users.
* Correlation: 'temp' and 'atemp' strongly correlate with bike usage; 'hum' and 'windspeed' weakly correlate.
* Seasonal Trends: Highest rentals in summer and fall.
* Yearly Growth: Higher rentals in 2018.
* Monthly Patterns: Sinusoidal with peak in summer, drop in spring.
* Holiday Impact: More variability on holidays, consistent on non-holidays.
* Weekday Usage: Consistent during weekdays, variable on weekends.
* Workingday Effect: Similar pattern to weekdays, suggesting minimal influence.
* Weather Influence: Highest demand in clear weather, lowest in light rain; no data for heavy rain.
* Strong Predictors: Season, weather, yearly growth, and month are strongest categorical predictors.

## Model Performance: 
* Using RFE for feature selection. Focus on Key Predictors: Prioritize 'temp', 'season', 'weather', 'yr', and 'mnth' in the model.
* Model Generalization: R-squared of 0.8 on test set, close to 0.81 on train set.
* Residuals Analysis: Outliers present, slight skewness, Q-Q plot deviation at extremes, Durbin-Watson around 2.
Model equation: cnt=4107 + 2541×weathersit_LightRain + 2033×yr + 785×temp + 563×mnth_Sep − 1317×season_sping − 821×holiday − 690×weathersit_Mist − 601×mnth_Jul 
* cnt: the total rental bike
# Positive correlated features
* weathersit_LightRain: weather condition: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
* yr: year
* temp: temperature in Celsius
* mnth_Sep: Sep of a year
# Negative correlated features:
* season_spring: Spring season in a year
* holiday: weather day is a holiday or not
* weathersit_Mist: weather condition: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
* mnth_Jul: Jul of a year

## Recommendations
> Business Strategy:
* Increase bike availability during light rain conditions as they positively impact rentals.
* Capitalize on the growing trend by planning for increased demand each year.
* Ensure more bikes are available during warmer temperatures and in September.
> Marketing:
* Reduce marketing efforts during spring and holidays as they negatively affect demand.
* Consider special promotions during July to counteract the seasonal dip in rentals.
> Weather Considerations:
* Prepare for higher demand during light rain conditions, but also ensure safety measures for riders.
* Monitor weather forecasts closely, especially for mist, to adjust bike availability accordingly.
> Model Validation: Although the model shows slight deviations in residuals, it remains robust; continue to monitor for any significant changes.
> Future Analysis: Collect more detailed weather data to refine predictions, especially for conditions like heavy rain which are currently unrepresented.

## Technologies Used
- Pandas version: 2.2.2
- Python version: 3.11.11 
- Matplotlib Version: 3.10.0
- Seaborn Version: 0.13.2
- Sklearn version: 1.6.1
- Statsmodel version: 0.14.4

## Contact
Created by @tuyettu1712

Dataset: https://drive.google.com/drive/folders/1K-7EfXaczB6XMqR9gg2xiNy8xnthpx4O
Data dictionary: https://drive.google.com/drive/folders/1K-7EfXaczB6XMqR9gg2xiNy8xnthpx4O 
