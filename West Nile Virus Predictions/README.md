# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 4: West Nile Virus

## Problem Statement

Recently there has been a surge in reported West Nile Virus (WNV) in Chicago.

The data science team of the Disease And Treatment Agency, division of Societal Cures In Epidemiology and New Creative Engineering had a meeting with the Chicago Department of Public Health's surveillance and control system to discuss how to tackle the situation. 

Undeniably, the easy way out will be to deploy pesticides over the entire city. However, doing so will be a costly affair and not to mention, environmentally unfriendly. The idea of targeting pesticide spraying can free up funds for other uses.

As data scientists in the (DATA-SCIENCE) department, we are task to derive an effective strategy and recommendation to curb the problem of a potential pandemic outbreak.

---

## Executive Summary

Our task is to develop a model to predict the likelihood of WNV being present so that targeted spraying of pesticides can be conducted and make use of the existing available datasets which have been collected sporadically over the years.

We will be examining 4 different datasets which records different types of information which is futher explained in the data dictionary.

Approached for this project:
- Data Cleaning
- Exploratory Data Analysis
- Featured Engineering & Data Preprocessing
- Modelling & Evaluation
- Cost Benefit Analysis
- Conclusions & Recommendations

---

## Data Dictionary
### Spray Dataset

|Feature|Type|Dataset|Description|
|:---|:---|:---:|:---|
|date|datetime|spray|date of pesticides spraying|
|time|object|spray|time of pesticides spraying|
|latitude|float|spray|north-south distance measurement (location) of spray|
|longitude|float|spray|east-west distance measurement (location) of spray| 

### Weather Dataset

|Feature|Type|Dataset|Description|
|:---|:---|:---:|:---|
|station|int|weather|different weather stations|
|date|datetime|weather|date of weather forecast|
|tmax|int|weather|maximum temperature (Fahrenheit)|
|tmin|int|weather|minimum temperature (Fahrenheit)|
|tavg|object|weather|average temperature (Fahrenheit)|
|depart|object|weather|temperature departure from normal (Fahrenheit)|
|dewpoint|int|weather|average temperature of dew point (Farenheit)|
|wetbulb|object|weather|average temperature of wet bulb (Farenheit)|
|heating|object|weather|heating - seasons begins in july (Based 65 Farenheit)|
|cooling|object|weather|cooling - seasons begins in january (Based 65 Farenheit)|
|sunrise|object|weather|time fo sunrise|
|sunset|object|weather|time fo sunset|
|codesum|object|weather|weather types|
|depth|object|weather|depth of snow - from ground (inches)|
|water1|object|weather|water equivalent (inches)|
|snowfall|object|weather|snowfall (Based on inches & tenths)|
|preciptotal|object|weather|water equivalent due to rainfall & melted snow (Based on inches & hundreths)|
|stnpressure|object|weather|average station pressure (Based on inches)|
|sealevel|object|weather|average sea level pressure (Based on inches)|
|resultspeed|float|weather|resultant wind speed (Based on miles per hour)|
|resultdir|int|weather|resultant direction (Based on whole degrees)|
|avgspeed|int|weather|average speed(Based on miles per hour)|

### Train & Test Dataset

|Feature|Type|Dataset|Description|
|:---|:---|:---:|:---|
|date|datetime|train & test|date that the wnv test is performed|
|address|object|train & test|approximate address of the location of trap (send to geocoder)|
|species|object|train & test|species of mosquitoes|
|block|int|train & test|block number of address|
|street|object|train & test|street name|
|trap|object|train & test|id of the trap|
|addressnumberandstreet|object|train & test|approximate address retuned from geocoder|
|latitude|float|train & test|latitude returned from geocoder|
|longitude|float|train & test|longitude returned from geocoder|
|addressaccuracy|int|train & test|accuracy returned from geocoder|
|nummosquitos|int|train & test|number of mosquitoes caught in trap|
|wnvpresent|int|train & test|whether west nile virus was present in this mosquitoes (1 - present, 0 - not present)|

---

## Data Cleaning
- Removal of duplicates rows or rows with too many missing values
- Imputing of Weather data collected from Station 2
- Imputing of temperature based on other features using calculatios e.g. TAVG
- For each row in Train & Test data, determine which is the nearest weather station (Station 1 / Station 2)
- Merging of Train & Test data with weather data from nearest weather stations (Station 1 / Station 2)

## Exploratory Data Analysis
- Correlation between weather features and number of Culex Mosquitoes trapped, WNV presence
- Date analysis between number of Culex Mosquitoes trapped and extent of WNV presence
- Multicollinearity between weather features
- Evaluation of the effect of spraying on WNV presence

## Featured Engineering and Data preprocessing 
- Creation of new features, relative humidity
- Creation of new features using polynomial features
- One-hot encoding of species, trap and codesum
- Handling of multi-collinearity features
- Top 40 correlated feature selected (excluding new features created)

## Modelling & Evaluation

Using 5 types of classification models:
- LogisticRegression()
- KNeighborsClassifier()
- RandomForestClassifier()
- AdaBoostClassifier()
- GradientBoostingClassifier()

To handle the imbalanced dataset, we instantaite oversampling using Synthetic Minority Over-Sampliung Technique (SMOTE) and for each model, we use GridSearchCV to find the best hyperparameters for each model.

We choose our best model based on best ROC_AUC score which measures whether our model could accurately classify whether wnv is present and Recall scores to measure how much the model correctly identify True Positives points.

### Model Results

|Models|Hyperparameters|Recall|ROC_AUC|
|:---:|:---:|:---:|:---:|
|LogReg|c: 4.8 / max_iter: 5000 / n_jobs: 3 / penalty: 'l2'|0.4817|0.7065|
|KNN|n_neigbors: 3|04233|0.0758|
|RF|max_depth: None / n_estimators: 120 |0.3430|0.8032|
|Ada|learning_rate: 0.5 / n_estimators: 200|0.6423|0.8082|
|Gb|learning_rate: 0.5 / n_estimators: 200|0.2487|0.8330|

## Cost Benefit Analysis

We understand that for a period of 14 years since the virus was first detected in New York, the WNV disease has cost a cumulative $778 million in health care expenditures and lost productivity (i.e. cost of approx. $56 million per year). Although there is a likelihood of underestimation, over 37,000 WNV cases have been report in these 14 years (i.e. on average more than 2,600 cases per year). On average, without taking into account inflation, cost (both medical and lost in productivity) per WNV case amount to approximately $21,000

If budget permits, it will be ideal to deploy mosquito control measures in the whole of Chicago daily throughout the year. However, we are aware that this method is not ideal in view of the cost involved. Even if budget is available, there will be a huge opportunity cost for not being able to set aside public funds for other use.

### Cost

On average, without taking into factors such as bulk discount, mosquito spray will cost $500 for every half acre per each time (source) or $182,500 for every half acre daily for the entire year.

Having said that, it is not necessary to incur such expenses because of the opportunity cost involved. Besides, even though WNV can cause disease in humans, to-date, there is no evidence of WNV transmission from person to person (source).

Hence, predictive modelling can be useful to guide decision makers when it comes to deploying mosquito control measures.

### Benefits

By utilising the model developed, we predicted the following occurences:
|Year|Total Locations|No. of WNV cases predicted| Percentage Class|
|:---:|:---:|:---:|:---:|
|2008|30,498|3,806|13%|
|2010|36,557|4,408|12%|
|2012|27,115|4,866|18%|
|2014|22,123|4,050|18%|

Overall, based on simple average, among all locations, WNV is likely to be present in 15% of the locations per year. So instead of costing $182,500 for every half acre per year, it will only cost us 15% of that amount, i.e. $27,375. The remaining 85% of the budget can be freed up for other critical use.

---

## Conclusions & Recommendations
### Conclusion

The best model successfully classifies the presence of WNV in our problem statement (predictions on the possibility of West Nile Virus occurrence on various locations in Chicago). Unfortunately, this model does not achieve the total eradication of mosquitoes. Most features of importance in the model are beyond our control (such as weather) and the datasets that we have are very imbalanced, so inference would not directly help reduce the cases of WNV present drastically.

However, this does not mean that the model is not helpful at all. We can identify common hotspots areas throughout the years can further monitor and target these areas by implementing further treatments.

While spraying is proven to be more effective cost of treatment compared to patients treament, it may also cause affects to the public health, hence a moderate, well planned strategy will help curb these issues by looking into targeted areas.

##### Best Model:
- For post: AdaBoost (learning_rate = 0.5, n_estimators = 200)

### Recommendations

While the model performs relatively well, they are many flaws and ways to further improve it's accuracy. Following are some recommendations that we can implement:

##### 1) More control measures
While surveillance and control systems are in place, our stakeholders can do regular checks on mosquito breeding areas weekly or fortnightly may help ensure tight monitoring of mosquito activities. 

Putting more effort to focus on hotspot areas and their surroundings will be beneficial to control the spread and increasing populations while identifying possible environmental factors that further boost reasons of high breeding in the area.

Ultimately destroying the mosquito and its breeding areas will reduce the number of West Nile virus. 

##### 2) Research & Development Investment
While spraying pesticides is a common way to rid mosquitoes, newer technologies and methods may further increase the efficiency. 

For example, deploying Aedes Aegypti experiment where genetically modified male mosquitoes are bred and release into the wild to pass on to its female counterpart gene that will require them an antibiotic to survive, else died in the wild. 

##### 3) Community Participation
Community involvement can also increase efficiency in supressing mosquito breeding. 

By educating the community on the dangers and effects of West Nile virus and how they can help stakeholders, e.g. making a report

## Reference:
- https://www.scientificamerican.com/article/first-genetically-modified-mosquitoes-released-in-u-s-are-hatching-now/

