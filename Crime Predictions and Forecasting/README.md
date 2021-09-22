# **Crime Prediction & Forecasting towards 2022**

## **Business Case**
Chicago State Police recently participated in the annual State Defense and Security Summit 2021 and have identified the need for a change in their policies on a city level. To increase the prevention effort for high crimes in the city and equipping proper skillsets and resources for their fellow officers moving forward.

As the first phase of revolutionizing policing work, they decided to set up a new department called PreCrime Task Force (PCTF) as representative of the force, informing and geared frontline officers towards potential crimes.

*‘Prevent, deter and detect crime’*


## **Problem Statement**
- To achieve success, we, Data Forensic Scientists, have been engaged by the state police to be the brains of the unit in predicting and forecasting different types of crimes and measured based on accuracy of the predictions.


## **Objectives**
 - Determine how a combination of machine learning algorithm can be used by Chicago State Police to detect, prevent, and solve crimes accurately and at a faster rate
 - Develop a model to predict and forecast crime rates per month to anticipate the allocation of resources and equipments


### **Project Approach**
Our task is to identify known crimes and develop a model to predict crimes rates to help inform state police officers for their preparation. 

Approached to this project are as follows:
1. Data acquisition from [Chicago Data Portal](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2)
2. Preliminary Analysis
3. Data Cleaning
4. Exploratory Data Analysis (EDA) 
5. Data Pre-processing
6. Modelling - Times Series & ML Regression
7. Conclusions & Recommendations

Data set used are available [here](https://drive.google.com/drive/folders/1sxTiW1wSCdiQ2ouKalelx5SCJVFSgYtk?usp=sharing)
## **Results**

**Theft crimes**

|Algorithm|Model|RMSE|MAE|
|---|---|---|---|
|Time Series|Holt Winters ES|1685.7299180626148|0.44666923637136496|
|ML Regression|XG Boost|384.89488424798094|0.09312016710289492|

---
**Battery crimes**

|Algorithm|Model|RMSE|MAE|
|---|---|---|---|
|Time Series|SARIMAX|605.2146932061636|0.1422582062036208|
|ML Regression|XG Boost|155.61552019459592|0.03465607850708874|

---
**Criminal Damage crimes**

|Algorithm|Model|RMSE|MAE|
|---|---|---|---|
|Time Series|SARIMAX|290.74088577983855|0.11893376700129941|
|ML Regression|XG Boost|46.644459765802345|0.017324809194114117|
---

- The cause of the time series error in Theft crime was an exponential decrease in crime rate which is not captured by the model accurately. 

- While time series has the function to forecast future values, its results while training model is questionable as it relies upon the endogenous feature and some exogenous features as explained in the notebook.

- Based on our domain knowledge, predicting crimes can be caused by other x-factors hence regression which can train on other important features gives us a better model accuracy as compared to the time series model
- **Best results: Using XG Boost from predictions**

## **Limitations**

1. Data collected lacks of sufficient information
2. The quality of the data is based on the accuracy and integrity of the person reporting the crime

## **Conclusions**

- As the first phase of deployment when can create a UI for officers to study information of crimes commited in the city and forecasted values to be well prepared for the day with the help of our model

- Predicting crimes before they happen is simple to understand, but it takes a lot more than understanding the concept to make it a reality. 

- The aim is to make crime prediction a reality and implement such advanced technology in real life to help assist the police prepare and prevent crimes from happening. 

- The deployment of such technology will fundamentally change the way police work in a much better and efficient manner. 

## **Recommendations**
Tools and information are needed to predict a crime before it occurs. State officers themselves are humans and may have limitations digesting, processing and infering big amount of data in order to predict crimes. 

Following are some recommendations they can take to increase the accuracy of predicting and forecasting crimes:



***1)  Working with experts***

- Other relevant parties should be involved in this project such as representatives from the government, academic and private organization to provide insightful information and domain knowledge of the individual industry.


***2)  Working with community***
 - At the moment, Chicago State Police may not have sufficient intel and types of equipment to aid them in understanding where crime may or potentially happen. Presently all information is based on crime reported via the main hotline channel. 

- By engaging the members of public to educate them of potential crimes and reporting to the police when issues arises. 

- This information provided will be useful to assist us in understanding crime patterns but also in detecting early signs of major crimes that may happen.

***3)  Research & Development***
- With the help of modern technology, Chicago State Police are able to reinforced their intelligence unit towards difference crimes in their city and well prepared to enforce law and ensure the safety of members of public.

- Surveillance equipments, crime report application are few of the modern technology tools that can be use assist in crime prediction.

## **Future Scope**
- This project presented the techniques and methods that can be used to predict crime. The scope of using different methods for crime prediction and prevention can change how enforcers work and prevent crimes.

- Using a combination of Machine Learning algorithms (ML) can substantially impact the overall functionality of the policing work. As we observed, substantial amount of information is required to ensure accuracy but in the future, combining ML algorithms, along with external informations and devices or equipments, our model can learn the pattern of previous crimes and understand what crime is, leading towards predicting future crimes accurately without human intervention.

- The scope of predicting crimes are endless. Aside from using just a regression and times-series tehcniques, we can also further look into the use of spatial data. This can be a starting point for our future study and bring about a revolution in the predicting, forecasting, detecting and prevention in policing work.


