# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2 - Ames Housing Data and Kaggle Challenge

## Problem Statement

Often times, house buyers would like to purchase houses within a given budget with maximum features and as owners, they would like to sell their houses (invesments) without making a loss.

As a Data Consultant engaged by a Housing & Property agents, they would like us to help improve their business within the next year by tasking us to design the best way to predict price of the house at sale based on historical datas collected for their business development team to further improve their business and provide useful and sound advice to clients intending to renovate their house for the purpose of selling them at for higher returns.

Areas of concern and findings to assist the agents would be:
- What features add the most value to a home?
- Given a set of features, what is the expected sale price of a house?
- Given a budget, what kind of house would one be able to afford based on our model?


As a consultant to CollegeBoard, identify which states have the best potential to increase SAT participation in the coming years and determine if they have the potential growth.

## Executive Summary (Things done in Jupyter Notebook):
- Exploratory Data Analysis
- Data cleaning and preprocessing on train.csv
- Data cleaning and preprocessing on test.csv 
- Data Modelling
- Observations
- Conclusions & Recommendations

## Data Dictionary

#### 1) Numerical - Continuous
|Attribute|Variable Type |Dataset|Description|
|---|---|---|---|
|**Lot Frontage**|*Continuous*|Ames Housing|Linear feet of street connected to property|
|**Lot Area**|*Continuous*|Ames Housing|Lot size in square feet|
|**Mas Vnr Area**|*Continuous*|Ames Housing|Masonry veneer area in square feet|
|**BsmtFin SF 1**|*Continuous*|Ames Housing|Type 1 finished square feet|
|**BsmtFin SF 2**|*Continuous*|Ames Housing|Type 2 finished square feet|
|**Bsmt Unf SF**|*Continuous*|Ames Housing|Unfinished square feet of basement area|
|**Total Bsmt SF**|*Continuous*|Ames Housing|Total square feet of basement area|
|**1st Flr SF**|*Continuous*|Ames Housing|First Floor square feet|
|**2nd Flr SF**|*Continuous*|Ames Housing|Second floor square feet|
|**Low Qual Fin SF**|*Continuous*|Ames Housing|Low quality finished square feet (all floors)|
|**Gr Liv Area**|*Continuous*|Ames Housing|Above grade (ground) living area square feet|
|**Garage Area**|*Continuous*|Ames Housing|Size of garage in square feet|
|**Wood Deck SF**|*Continuous*|Ames Housing|Wood deck area in square feet|
|**Open Porch SF**|*Continuous*|Ames Housing|Open porch area in square feet|
|**Enclosed Porch**|*Continuous*|Ames Housing|Enclosed porch area in square feet|
|**3Ssn Porch**|*Continuous*|Ames Housing|Three season porch area in square feet|
|**Screen Porch**|*Continuous*|Ames Housing|Screen porch area in square feet|
|**Pool Area**|*Continuous*|Ames Housing|Pool area in square feet|
|**Misc Val**|*Continuous*|Ames Housing|Dollar-Value of miscellaneous feature|
|**SalePrice**|*Continuous*|Ames Housing|Sale price $$ (target)|

#### 2) Numerical - Discrete
|Attribute|Variable Type |Dataset|Description|
|---|---|---|---|
|**Id**|*Discrete*|Ames Housing|Unique ID for each property|
|**Year Built**|*Discrete*|Ames Housing|Original construction date|
|**Year Remod/Add**|*Discrete*|Ames Housing|Remodel date (same as construction date if no remodeling or additions)|
|**Bsmt Full Bath**|*Discrete*|Ames Housing|Basement full bathrooms|
|**Bsmt Half Bath**|*Discrete*|Ames Housing|Basement half bathrooms|
|**Full Bath**|*Discrete*|Ames Housing|Full bathrooms above grade|
|**Half Bath**|*Discrete*|Ames Housing|Half baths above grade|
|**Bedroom AbvGr**|*Discrete*|Ames Housing|Bedrooms above grade (does NOT include basement bedrooms)|
|**Kitchen AbvGr**|*Discrete*|Ames Housing|Kitchens above grade|
|**TotRms AbvGrd**|*Discrete*|Ames Housing|Total rooms above grade (does not include bathrooms)|
|**Fireplaces**|*Discrete*|Ames Housing|Number of fireplaces|
|**Garage Yr Blt**|*Discrete*|Ames Housing|Year garage was built|
|**Garage Cars**|*Discrete*|Ames Housing|Size of garage in car capacity|
|**Mo Sold**|*Discrete*|Ames Housing|Month Sold (MM)|
|**Yr Sold**|*Discrete*|Ames Housing|Year Sold (YYYY)|

#### 3) Categorical - Nominal
|Attribute|Variable Type |Dataset|Description|
|---|---|---|---|
|**PID**|*Nominal*|Ames Housing|Parcel identification number - can be used with city web site for parcel review|
|**MS SubClass**|*Nominal*|Ames Housing|Identifies the type of dwelling involved in the sale|
|**MS Zoning**|*Nominal*|Ames Housing|Identifies the general zoning classification of the sale|
|**Street**|*Nominal*|Ames Housing|Type of road access to property|
|**Alley**|*Nominal*|Ames Housing|Type of alley access to property|
|**Land Contour**|*Nominal*|Ames Housing|Flatness of the property|
|**Lot Config**|*Nominal*|Ames Housing|Lot configuration|
|**Neighborhood**|*Nominal*|Ames Housing|Physical locations within Ames city limits (map available)|
|**Condition 1**|*Nominal*|Ames Housing|Proximity to various conditions|
|**Condition 2**|*Nominal*|Ames Housing|Proximity to various conditions (if more than one is present)|
|**Bldg Type**|*Nominal*|Ames Housing|Type of dwelling|
|**House Style**|*Nominal*|Ames Housing|Style of dwelling|
|**Roof Style**|*Nominal*|Ames Housing|Type of roof|
|**Roof Matl**|*Nominal*|Ames Housing|Roof material|
|**Exterior 1st**|*Nominal*|Ames Housing|Exterior covering on house|
|**Exterior 2nd**|*Nominal*|Ames Housing|Exterior covering on house (if more than one material)|
|**Mas Vnr Type**|*Nominal*|Ames Housing|Masonry veneer type|
|**Foundation**|*Nominal*|Ames Housing|Type of foundation|
|**Heating**|*Nominal*|Ames Housing|Type of heating|
|**Central Air**|*Nominal*|Ames Housing|Central air conditioning|
|**Garage Type**|*Nominal*|Ames Housing|Garage location|
|**Misc Feature**|*Nominal*|Ames Housing|Miscellaneous feature not covered in other categories|
|**Sale Type**|*Nominal*|Ames Housing|Type of sale|

#### 4) Categorical - Ordinal
|Attribute|Variable Type |Dataset|Description|
|---|---|---|---|
|**Lot Shape**|*Ordinal*|Ames Housing|General shape of property|
|**Utilities**|*Ordinal*|Ames Housing|Type of utilities available|
|**Land Slope**|*Ordinal*|Ames Housing|Slope of property|
|**Overall Qual**|*Ordinal*|Ames Housing|Rates the overall material and finish of the house|
|**Overall Cond**|*Ordinal*|Ames Housing|Rates the overall condition of the house|
|**Exter Qual**|*Ordinal*|Ames Housing|Evaluates the quality of the material on the exterior |
|**Exter Cond**|*Ordinal*|Ames Housing|Evaluates the present condition of the material on the exterior|
|**Bsmt Qual**|*Ordinal*|Ames Housing|Evaluates the height of the basement|
|**Bsmt Cond**|*Ordinal*|Ames Housing|Evaluates the general condition of the basement|
|**Bsmt Exposure**|*Ordinal*|Ames Housing|Refers to walkout or garden level walls|
|**BsmtFin Type 1**|*Ordinal*|Ames Housing|Rating of basement finished area|
|**BsmtFin Type 2**|*Ordinal*|Ames Housing|Rating of basement finished area (if multiple types)|
|**Heating QC**|*Ordinal*|Ames Housing|Heating quality and condition|
|**Electrical**|*Ordinal*|Ames Housing|Electrical system|
|**Kitchen Qual**|*Ordinal*|Ames Housing|Kitchen quality|
|**Functional**|*Ordinal*|Ames Housing|Home functionality (Assume typical unless deductions are warranted)|
|**Fireplace Qu**|*Ordinal*|Ames Housing|Number of fireplaces|
|**Garage Finish**|*Ordinal*|Ames Housing|Interior finish of the garage|
|**Garage Qual**|*Ordinal*|Ames Housing|Garage quality|
|**Garage Cond**|*Ordinal*|Ames Housing|Garage condition|
|**Paved Drive**|*Ordinal*|Ames Housing|Paved driveway|
|**Pool QC**|*Ordinal*|Ames Housing|Pool quality|
|**Fence**|*Ordinal*|Ames Housing|Fence quality|

## Conclusions & Recommendations

#### Conclusion  
Based on the best fit model, I have identified the following features to increase the values of the of the sales price:
- year_built
- year_remod/add
- mas_vnr_area
- bsmtfin_sf_
- total_bsmt_sf
- bsmt_qual_TA
- bsmtfin_type_1_GLQ
- 1st_flr_sf
- gr_liv_area
- full_bath
- totrms_abvgrd
- fireplaces
- garage_cars
- garage_area
- neighborhood_NridgHt
- overall_qual_8
- overall_qual_9
- mas_vnr_type_None
- exter_qual_Gd
- exter_qual_TA
- foundation_PConc
- kitchen_qual_TA
- fireplace_qu_NA
- garage_finish_Unf

Through observations and analysis, the Ridge model is the best performing model in terms of R2 scores and RMSE as compared to other model. The featured mentioned are the have the highest correlation to determine the factor of sales price. 

#### Recommendations  

Most of the features are available when purchase the house and owners have no control over the given choice. Instead they can increase the sales price by targeting the functionality of the features such as increase the overall quality of the house to 8 - 9 or renovate the house with additional features|




