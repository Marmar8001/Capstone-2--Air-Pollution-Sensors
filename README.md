## Predicting Air Pollution Real Data Using Sensor Data & Environmental Factors:
The sensor manufacturing company, wants to understand the effects of temperature and humidity on predicting air pollution compounds like CO, NOX, NO2 and Non-Methanic Hydrocarbons. Knowing the effect of environmental factors is very important in calibrating sensor to predict real pollution indexes. In this  project, I will predict real air pollution data for CO, NOX, NO2 and non-methanic hydrocarbons using sensor data, temperature and humidity. In that way, calibration of sensors will be much more accurate and can count for temperature and humidity effects on sensors performance. The project will be devided to 4 parts: 1) Data wrangling, 2) Exploratory Data Analysis, 3) Data Preprocessing and Model Trainning, 4) Modeling Case Studies.

### Data:
The dataset includes 9358 instances of hourly averaged responses from an array of 5 metal oxide chemical sensors embedded in an Air Quality Chemical Multisensor Device.
The device was located on the field in a significantly polluted area, at road level,within an Italian city. Data were recorded from March 2004 to February 2005 (one year)representing the longest freely available recordings of on field deployed air quality chemical sensor devices responses. Ground Truth hourly averaged concentrations for CO, Non Metanic Hydrocarbons, Benzene, Total Nitrogen Oxides (NOx) and Nitrogen Dioxide (NO2) were provided by a co-located reference certified analyzer.  So, both true values and sensors values are available.The Temperature, absolute humidity and relative humidities are also provided.

### 1) Data Wrangling:
The data has some invalid numbers as -200 in the datset. All of these invalid numbers replaced by Nan values. After doing that, the dataset was assessed and showed around 17% missing values in real data for CO, NOx and NO2 and 4% missing values in sensor data for CO, NOX and NO2 with humidity and temperature. Non methanic hydrocarbon real data had more than 90% missing values because they stopped to measure it at early points. The histogram of data did not show any obvious outliers.Plotting sensor vs real values showed some kind of linear relationship between sensor and true values for the CO but it was hard to understand sensor and true values relationship for NOX and NO2 especially for NO2.

### 2) Exploratory Data Analysis:
The data heatmap showed strong correlation between NO2 sensor, humidity and temperature. The box plots showed less pollutions in weekends versus weekdays as expected. The correlation of real data vs sensor data showed strong effects of humidity and temperature. The sensor vs real data for CO and non-methanic hydrocarbons showed strong linear trend while NO2 and NOx real and sensor data did not show linear trend.

### 3) Data Preprocessing & Model Training:
Three model was tried for predicting real data based on sensor data, temperature and humidity for CO, NOX, NO2 and NMH.(Linear Regression, Decision Tree and Ransom Forest) 
* Linear regression model was selected to predict real data using sensor data, temperature and humidity. The linear model was slightly less accurate than random forest but the difference between models accuracy was minimal and less complicated model (linear regression model was selected.) The temperature had positive effect while humidity had negative effect on predicting real data from sensor data for CO. 
* Decision tree model was selected to predict real data from sensor data for NOX. Decision tree model has much better r2 score and mean absolute error than linear regression model. Sensor data had 80% importance in predicting real data while temperature had 15% and humidity had 5% feature importance.
* Random forest model was selected to predict real data from sensor data for NO2. Random forest model has much better r2 score and mean absolute error than decision tree and linear regression model. Sensor data had 40% feature imporatnce while humidity and temperature had 40% and 20% importance in predicting NO2 real data.
* Linear regression model was selected to predicting non methanic hydrocarbons real data as it had less complexity ang good mean absolute error and r2 score. Temperature and humidity had minimal effect in predicting real data from sensor data for non methanic hydrocarbons.

### 4) Modeling Case Studies:
In the last part, the humidity effect on real data prediction was investigated in average sensor and temperature data. The results showed that:
* CO real data decreased by increasing humidity. The change between minimum and maximum humidity level was around 30%.
* NOX real data decreased by increasing humidity just in lower ranges of humidity (0.2-0.75). The change between minimum and maximum humidity level was around 50%.
* NO2 real data decreased significantly by increasing humidity. The change between minimum and maximum humidity level was around 60%.
* NMH real data did not change by increasing humidity. So, humidity did not affect non methanic hydrocarbons real data.

### Next Steps:
Other important environmental factors can be added to predict more accurately real data from sensor data like wind directions.


