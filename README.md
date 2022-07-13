# 1  SyriaTel Customer Churn Prediction

Author- Kyunghwan William Kim

## 1.1  Overview

The main focus of this project is to build a classifier to predict whether a 
customer will soon stop doing business with SyriaTel, a telecommunications 
company. The data set which was downloaded from Kaggle consists of 20 features
and 3333 rows containing SyriaTel's churn metrics.The process outline 
initiates by identifying the top attributes of churn and then creating a final
machine learning model to predict whether or not a customer will soon churn. 
Several machine learning models were created and their performances were 
compared to decide on a final predictive model that the stakeholder can use on
their current database.

## 1.2  Business Understanding

SyriaTel is interested in reducing how much money is lost because of customers
who don't stick around very long. The question to answer is: are there any 
predictable patterns here?

Customer churn is a major problem and one of the most important concerns for 
large companies. Due to the direct effect on the revenues of the companies, 
especially in the telecom field, companies are seeking to develop means to
predict potential customer to churn. Therefore, finding factors that increase
customer churn is important to take necessary actions to reduce this churn. 
The main contribution of our project is to develop a churn prediction model
which assists telecom operators to predict customers who are most likely
subject to churn.

## 1.3  Method

The objective will be achieved by first assessing the feature importance on 
the below attributes and determining which tend to be the strongest predictors
of churn. Then apply these attributes to several classification machine 
learning models to classify at risk customers in the present and in the 
future.

### 1.3.1  Method Outline

After analyzing the data the project is identified as a classification 
problem. The target variable 'churn' creates a binary classification.
For this instance the balance of the target variable will be investigated
Since the target variable is imbalanced, the Accuracy score will not be used, 
instead the Recall score will be more important due to the problem at hand.

### 1.3.2  Type Errors

The nature of this problem is framed by the fact that losing current customers
is less expensive than gaining new customers. Therefore, it is much better to
retain the customers that the company currently has rather than to acquire new
customers.

Incorrectly classifying a false negative would pose a higher threat than a 
false positive because a false negative would mean that the reality of a 
customer canceling would have been overlooked. The occurrence of the 
false-negative occurring is referred to as a type two error. In order to rank 
the classifiers on how well they minimized false negatives, measurement of
recall has been utilized.

## 1.4  Exploratory Data Analysis

Most of our features have a numeric datatype except for state, phone number, 
international plan, & voicemail plan. Let's investigate these features to 
classify as either categorical or continuous.

### 1.4.1  Cleaning and Preprocessing

Cleaning and Preprocessing Outline
1. Replace ' ' with '-'
2. Check for null and duplicated values
3. Inspect Unique values of columns to identify potential errors or null values
4.Convert all yes,no object values into integer values
5. Calculate the total_net_minutes, total_net_calls & total_net_charge to 
reduce the number of features
6. Drop all repeated features and irrelevant columns

### 1.4.2  Investigate Features

1. Churn
2. State
3. Account Length
4. Area code
5. International Calls
6. Voice Messages
7. Customer Service Calss
8. Net Charges
9. Investigate Correlations

### 1.4.3  Data

In this sample dataset of the population of SyriaTel clients, the churn rate 
is 14.5%. The number one reason of churn in the telecom industry is customer 
service issues. By identifying the early indicators of customer 
dissatisfaction and addressing them boldly to achieve utmost customer 
satisfaction.

Using a Pearson's correlation, the following features had the highest 
correlations to churn

1. total_net_charge
2. customer_service_calls
3. total_day_minutes
The Pearson correlation coefficient only measures linear correlations, thus 
categorical features were not addressed.

## 1.5  Modeling

### 1.5.1  Model 1: Buidling a Vanilla Model using Logistic Regression
Recall Score: 14

### 1.5.2  Model 2: K-Nearest Neighbors
Recall Score: 27

### 1.5.3  Model 3: Random Forest Model
Recall Score: 94

##### Fine-Tune Model Using GridSearch CV
Recall Score: 95.32

##### Feature Importance
Using Feature Importance, we can see that total day charge is the most 
important feature, we can assume that total net charges are the most 
important, followed by number of customer service calls, and whether a 
customer has an international plan or not.

### 1.5.4  Model 4: XGBoost
Recall Score: 74

## 1.6  Conclusions

The importance of this type of research in the telecom market is to help 
companies make more profit. It has become known that predicting churn is one 
of the most important sources of income to telecom companies. Hence, this 
research aimed to build a system that predicts the churn of customers in 
SyriaTel telecom company. Four seperate models were created,

1. Logistic Regression
2. K-Nearest Neighbors
3. Random Forest
4. XG Boost

Our Random forest model had the highest recall score of 95.32% and was chosen
to be the best and final model.

### 1.6.1  Recommendations

Based on the feature analysis and the results from the final model it is clear
that customer service calls and day call charges have the strongest impact on 
customer churn. SyriaTel can do the following to reduce churn:

Customers who called customer service more than three times should be reviewed
with more importance. Track metrics from customer service calls. Are clients 
calling about the same issues? Once we know why these clients are calling we
can better alleviate their pain by addressing and correcting these issues.

Re-evaluate pricing structure for day calls. Consider a tiered pricing
structure past a certain dollar amount

The international plan is not marketed effectively less than 10% of customers
have the international plan and are paying the same rate as customers without
the plan. The international plan has to be updated.