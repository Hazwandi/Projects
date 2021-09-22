# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

## Overview

For the first project, we're going to take a look at aggregate SAT and ACT scores and participation rates in the United States. We'll seek to identify trends in the data and combine our data analysis with outside research to address the problem statement.

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math. The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section and they have different score ranges.

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude. Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

## Problem Statement

As a consultant to CollegeBoard, identify which states have the best potential to increase SAT participation in the coming years and determine if they have the potential growth.

## Executive Summary (Things done in Jupyter Notebook):
- SAT Data Cleaning
- SAT / ACT Requirement Data Cleaning
- ACT Data Cleaning
- Exploratory Data Analysis
- Data Visualization
- Observations
- Conclusions & Recommendations

## Data Dictionary

#### 1) sat
|Feature|Type|Dataset|Description|
|---|---|---|---|
|index|int|sat_2017, sat_2018, sat_2019|Position in the list|
|state|object|sat_2017, sat_2018, sat_2019|Name of state in US|
|participation_rate|float|sat_2017, sat_2018, sat_2019|Percentage participation rate|
|ebrw|int|sat_2017, sat_2018, sat_2019|Evidence-based Reading and Writing score SAT|
|math|int|sat_2017, sat_2018, sat_2019|Math score SAT|
|total|int|sat_2017, sat_2018, sat_2019|Sum of EBRW and Math scores for SAT|
|year|int|sat_2017, sat_2018, sat_2019|Year of data|
|sat_required|object|sat_act_req|Requirement status for SAT in state|
|act_required|object|sat_act_req|Requirement status for ACT in state|

#### 2) act
|Feature|Type|Dataset|Description|
|---|---|---|---|
|index|int|act_2017, act_2018, act_2019|Position in the list|
|state|object|act_2017, act_2018, act_2019|Name of state in US|
|participation_rate|float|act_2017, act_2018, act_2019|Percentage participation rate|
|composite|int|act_2017, act_2018, act_2019|AVerage score for 4 test (English, Math, Reading and Science) in ACT|
|year|int|act_2017, act_2018, act_2019|Year of data|

#### 3) participation_comb
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|sat, act|Name of state in US|
|sat_participation_2017|float|sat_2017, sat_2018, sat_2019|Percentage participation rate for sat in 2017|
|sat_participation_2018|float|sat_2017, sat_2018, sat_2019|Percentage participation rate for sat in 2018|
|sat_participation_2019|float|sat_2017, sat_2018, sat_2019|Percentage participation rate for sat in 2019|
|act_participation_2017|float|act_2017, act_2018, act_2019|Percentage participation rate for act in 2017|
|act_participation_2018|float|act_2017, act_2018, act_2019|Percentage participation rate for act in 2018|
|act_participation_2019|float|act_2017, act_2018, act_2019|Percentage participation rate for act in 2019|

#### 4) scores_comb
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|sat, act|Name of state in US|
|total_2017|float|sat_2017, sat_2018, sat_2019|SAT total scores in 2017|
|total_2018|float|sat_2017, sat_2018, sat_2019|SAT total scores in 2018|
|total_2019|float|sat_2017, sat_2018, sat_2019|SAT total scores in 2019|
|composite_2017|float|act_2017, act_2018, act_2019|ACT composite scores in 2017|
|composite_2018|float|act_2017, act_2018, act_2019|ACT composite scores in 2018|
|composite_2019|float|act_2017, act_2018, act_2019|ACT composite scores in 2019|

#### 5) state_population
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|state_population|Name of state in US|
|population_size|float|state_population|State population size|

## Conclusions & Recommendations

#### Conclusion  
Through observations and analysis of data, there is a constant increase in the participation rate for SAT and most students scores well above the average in respective subjects. Therefore, we should leverage on the trend and further increase participation with target states who are doing well but at the mid of the the spectrum fulfilling the following criterias:  
- States pariticipation rate between 50th to 75th percentile
- States total scores above national average (1059) above (523) and progressive score above 2017
- States evidence based reading and writing scores above (523) and progressive score above 2017
- States math scores above (528) above (523) and progressive score above 2017
- Larger population size

Based on collected data, target states are as follows:  
- California (drop)
- Pennsylvania
- Oregon  
- Indiana

After doing some outside research, we find out that state of California has a lot of underlying issues. While potentially the best to grow due to its sheer population and market in standardized test, the decision made by University of California to drop the current SAT & ACT have signal the demise of the test with other colleges following suite.


#### Recommendations  

With the information of California, I am dropping the state as from the final selection.

Final decision on target state:
- Pennsylvania  
- Oregon  
- Indiana

In order to achieve a higher participation, CollegeBoard can also review some recommendations to help boost their presence among the students

##### 1) Implementation of current SAT school day emphasize on target states  
Generally SAT test are conducted on saturdays which may be incovenient for some student as well as testing center who normally operates on weekdays basis. By offer SAT school days, students are allow to take exams and their covenience and comfort in their own school. At the same time helping teachers prepare,follow progress, coach and support the students before the actual test.  

##### 2) Provide help to students by offering PSAT services  
While it does not count toward the final score for SAT, it is a qualifying test for National Merit scholarship and help serve as a guidepost for college admission journey with free resouces, practices and guidance counselors. It helps student build their confidence and have a sense of the preparation need to score for the test.  

##### 3) Sharing of best practices
Some schools may not have the knowledge to increase and improve SAT scores and participation. By consolidating and sharing of best practices among schools that shows significant boost, it will build a community of school badly affected to follow suit. 

Not all best practices are suited for individual schools but areas where it can be implement, these schools can take advantage of it.

#### Reference:
- https://www.highereddive.com/news/u-of-california-eliminates-sat-act-as-admissions-requirement/578373/
- https://collegereadiness.collegeboard.org/sat/k12-educators/sat-school-day
- https://collegereadiness.collegeboard.org/psat-nmsqt-psat-10/inside-the-test
- https://www.forbes.com/sites/noodleeducation/2015/10/12/does-the-psat-really-matter/?sh=4681d1058585
- https://reports.collegeboard.org/pdf/2019-georgia-sat-suite-assessments-annual-report.pdf
- https://reports.collegeboard.org/pdf/2019-texas-sat-suite-assessments-annual-report.pdf



