# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP

## Problem Statement
As graduating students in data science, we were approached by a group of investors (X) who notice that the subreddit forum could potentially be an alternative way to analyze the fluctuation in their investment of GameStop (GME) and Dogecoin by understanding its behaviour.

Their reasoning behind exploring this alternative was largely due to the recent trend of investors trading based on comments made by users on social media platform and the influence of big figures in the market.

We were task to identify words from post or title that may likely determine an increase in investment value at a certain period and classifying post fromm which source it came from.

## Executive Summary (Things done in Jupyter Notebook):
We will be examining 2 different subreddits GameStop (r/gme) and Dogecoin (r/dogecoin). While the data are very similar by default, there are differences in each individual characteristic. 

The goal is to understand if we are able to classify each unseen post according to the right subreddit given the nature of its post.

Approach for this project:
- Data acquisition using PushShift's API
- Preliminary exploratory data analysis (raw data)
- Data cleaning & pre-processing
- Post exploratory data analysis (clean data)
- Data Vectorization
- Modeling & Evaluation (Finding best model with high score)
- Conclusions & Recommendations

## Data Dictionary
|Features|Types|Datasets|Descriptions|
|---|---|---|---|
|id|object|r/gme, r/dogecoin|subreddit userid|
|author|object|r/gme, r/dogecoin|subreddit username|
|created_utc|object|r/gme, r/dogecoin|date and time of post|
|subreddit|object|r/gme, r/dogecoin|subreddit group|
|selftext|object|r/gme, r/dogecoin|subreddit post|
|title|object|r/gme, r/dogecoin|subreddit title|

## Conclusions & Recommendations
### Conclusion
We identify requirements of the problem statement (approach using Natural Language Processing (NLP) and events that cause an increase in share price) needed and extracted the data from individual subreddits (r/GME & r/dogecoin). 

Preliminary exploratory data analysis was done to understand the characteristic such as common words, frequency and distribution of words and characters for both post and title. We identify some noises and proceeded to clean, pre-process the data. We conducted another EDA to examine changes from the initial data set and notice that the data changes especially top words.

We tested using 2 different types of vectorizer (CountVectorizer and TF-IDF) and 3 types of classification models (Logistic Regression, MultinomialNB and Random Forest) using GridSearchCV and it has identified the best model based on F1 score and ROC-AUC metrics.

##### Best Model:
- For post: TF-IDF (n-gram:(1, 1), min_df=2) with Random Forest (max_depth=None, n_estimators=160)
- For title: TF-IDF (n_gram: (1, 1), min_df=2) with Logistic Regression (C=1.1, max_iter=4000, penalty='l2')

Through our observation the model performs relatively well for both post and title with an F1 score of 89.3% and ROC-AUC score of 93.3% for post whereas F1 score of 87.3% and ROC-AUC score of 89.9% for title, small difference in comparison to each other.

While our data is imbalanced, the results have clearly shown that it is able to classify post with a relatively high score. The model produce would be useful for the group of investors to identify the classification of based on an unseen post and understand the trends within the the community based on words used.

### Recommendations

While the model performs relatively well, they are many flaws and ways to further improve it's accuracy. Following are some recommendations that we can implement:

##### 1) Train more data to improve modeling
The current data is based on a recent event. If the model is trained with data from other similar events, we may be able to improve the score further and differentiate 2 different data clearly.

##### 2) Using other sources of media to further understand their behaviour
As unstructured data is now explored in many real-time businesses and depending on the cause of fluctuation of individual price, other medias can be explored, for example, financial blogs and news sites 

##### 3) Using more complex models
We can build more complex model using to minimize false positive and false negative by using other types of vectorizer such as Word2Vec and Bert.

## Reference:
- Subreddit 1 - 'GameStop': https://reddit.com/r/gme
- Subreddit 2 - 'Dogecoin': https://reddit.com/r/Dogecoin
- PushShift's API: https://github.com/pushshift/api
- https://blog.insightdatascience.com/how-to-solve-90-of-nlp-problems-a-step-by-step-guide-fda605278e4e
- https://neptune.ai/blog/exploratory-data-analysis-natural-language-processing-tools
- https://towardsdatascience.com/the-5-classification-evaluation-metrics-you-must-know-aa97784ff226
