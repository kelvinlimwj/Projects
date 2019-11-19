# Problem Statement
To develop a predictive model that will forecast the probability of WNV presence in 138 mosquito traps around Chicago over the course of a season. WNV is a communicable disease that is spread through its most common vector, mosquitoes.

# Executive Summary
- Data cleaning and EDA done on the train/test, weather and spray datasets
    - Train.csv was split into a training set and testing set. EDA was done on the training set.
- General observed trends:
    - WNV incidences spiked in July and August, the summer months in Chicago.
    - The spikes corresponds with increase in temp. and also humidity.
    - During the summer months, the number of days between rain days generally increases as well.
- Visualization of spatial data was done to observe the trap locations, concentration of WNV incidences, and spray locations.
    - It was found that O'Hare Airport was a major hotspot, with the other hotspot being in the River Grove/Belmont Terrace area. These areas either have multiple bodies of water, or are areas with a lot of greenery.
- Cost-benefit analysis done for spraying pesticide. It was concluded that usage of pesticide was not worth the amount of money for the effect it created.
- Modelling was done with various classification models, with the best being an XGBoost model.

# Data Dictionary
|Feature|Type|Usage in model|Description|
|-------|----|-----|-----------|
|WnvPresent|*int*|Target Variable|The target variable; whether the sample contains WNV (1) or not (0)|
|Longitude, Latitude|*float*|Predictor Variable|Coordinates of the location of the traps|  
|Tavg|*float*|Predictor Variable|Avg. temperature on that day|
|Tavg_rolling|*float*|Predictor Variable|3, 7, 14 days rolling avgs. for Tavg|
|DewPoint|*float*|Predictor Variable|A measure of the humidity|
|DewPoint_rolling|*float*|Predictor Variable|3, 7, 14 days rolling avgs. for Tavg|
|Days_since_rain|*int*|Predictor Variable|The number of days since a rain day|

# Conclusion
- Danger periods are during the summer months of Chicago, i.e. July and August
- Clear seasonality observed for weather data
- Spraying does not provide any benefits to justify the cost
- Maybe instead of focusing on mosquito surveillance, birds should be considered too as they are WNV carriers as well


**Limitations**
- Rather than sampling mosquito population and having a binary classification for WnvPresent, an improvement may be to show the number of mosquitos carrying WNV so that a rate can be calculated.
- Bird data is not given, which is quite important data as they are carriers as well.


**Further work**
- Usage of neural networks may provide an improvement to model performance.