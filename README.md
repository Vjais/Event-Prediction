# Event-Prediction
<h1>Tool and Language</h1>
​Jupyter Notebook and Python 3.6
<h1>● Problem Statement</h1>
The dataset samplekkm is about events that happened around particular location in a
duration of 3 months i.e January to March.I tried to create a classifier for predicting the
type of event.The classifiers will be judged on their accuracy and precision.
<h1>● Data Cleaning and Analysis</h1>
1) Imported the dataset using pandas as crm and created copy in crm2.
2) Dropped the columns with 100% missing values.
3) Splitted the column EVENTTYPE into cause and reason in order to identify the
number of events.
4) Filled the missing values using fillna() in separate dataframes for column
occurrencetime using ‘00:00:00​’ as it cannot have nan values else will create issue
while splitting,filled column Cause with ‘Unknown’ ​as the events were reported but
was not labeled,filled column loccode and zone with 0.
5) Merged the dataframe into crm2.
6) Converted the data type into Category which were initially object in order to treat
each event as separate.
7) Dropped unnecessary columns from crm2 which were not relevant to event
prediction..
8) Splitted OccuranceDate into weekday and weekends to check the event happened
the most during a week.
9) Extracted hours from Occurencetime to check the time when maximum event
happened.
10) Sorted the target variable to check the occurence of type of event.
<h1>● Event Prediction using Models</h1>
1) Created dummy features for categorical data. This will result in large number of
features.We choose top 150 features to avoid problems because of high
dimensional data. Then we split the data into training set, development set and test
set. The data is divided into 70:10:20 ratio.
2) Function getAccuracy() to get development accuracy for a given classifier.
3) Tuned parameters of classifiers based on their performance on development set.
The classifiers used are: Random Forest ,SVM and Decision Tree.
4) Accuracy achieved is 41% for decision tree,35% for svm,36% for Random
Forest.Clearly,Decision tree gives the best result.The reason for low accuracy is as
the target variable is highly imbalanced and giving weights or sampling would create
bias in result.
