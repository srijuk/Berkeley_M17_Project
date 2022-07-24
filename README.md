# Comparing the Machine Learning Classifiers

## Introduction
The goal is to compare the perfomance of the following classifiers using scikit learn (sklearn)
1. K Nearest Neighbors (KNN)
2. Linear Rrgreession
3. Decision Tress
4. Support Vector Machine

The data is from a UCI repository (https://archive.ics.uci.edu/ml/datasets/bank+marketing) which was from a Portugese banking institution and is a collection of results of multiple marketing campaigns. The task is to correctly classify customers who would subscribe to a bank deposit. 

The campaign data was ignored for the task and only the banking details of the clients were used to classify customers who would subscribe to a deposit.

## Methodology
The data is supplied as full and trimmed down versions. The full dataset was used for all classifiers except for SVM classifier where the trimmed down version of the dataset was used.

The data was first split into train and test datasets using stratify on the 'y' column, which is the target column where the customer subscribed to a deposit or not.

Then the data for non numeric columns was encoded using the TargetEncoder and later the age and campaign columns was sacled using their respective means and standard deviations.

### Some basic inferences such as below could be made from the initial charting

1. Younger people subscribed to the deposits more than the older people

2. People who had more years of education like a university degree were more likely to subscribe to the deposit.

3. People who own housing are more likely to subscribe to deposit than who don't

4. People with no loans are more likely to subscribe to a deposit

5. Older people were called up more times than younger clients

6. Some people were contacted more than 50 times

7. The number of times a campaign was conducted had a negative impact on the subcribing to a deposit

## Conclusions

GridSearchCV was used to find the best estimator for each classifier. 

The <b> logisticRegression </b> classifier trained well using the 'roc_auc' scoring method while it gave worse results using a default or any other scoring.

The <b> KNN classifier </b> was faster to train than the LogisticRegression classifier with the best nearest neighbor as 43 and had higher training accuracy and recall score but lower test accuracy than the LogisticRegression 

The <b> decision tree classifier </b> trained faster than the LogisticRegression and KNN classifiers but gave poorer Recall and Precision scores even though the training and test accuracy were better.

The <b> SVM classifier </b> took much longer on the full data set and hence the trimmed down version of the dataset was used to train and measure the accuracy of the test data. The classifer gave lesser recall score but better precision score with the best kernel function as 'poly' with a degree of 2. 
