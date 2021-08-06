![mobile_network](./images/mobile_network.png)

# SyriaTel Customer Churn Project

## Table of Contents
* [Overview](#overview)
* [Business Problem](#business-problem)
* [Data](#data-sources-and-understanding)
* [Analysis](#analysis)
* [Features](#features)
* [Project Structure](#project-structure)


## Overview
Across the telecommunication industry, customer churn is one of the most important concerns that directly affect a telecommunication company's business. Hence, companies that are able to successfully predict customer churn will be able to allocate capital and resources more efficiently and thereby improve profitability. 

This project analyzes customer churn (customers leaving the provider) data from SyriaTel, a telecommunications provider, identifying what type of customers were churning and developing a model that could predict whether a customer is likely to churn. SyriaTel can use this analysis to focus their efforts in modifying certain cellular plans, especially in key states such as NJ, CA, TX, MD, and SC. In addition, SyriaTel can use the model to help identify which customers are likely to churn.

## Business Problem
SyriaTel has been facing a customer churn problem. Based on a customer survey data, SyriaTel had a churn rate of ~14%, while the typical churn rate is between [0.5-5%](https://stlpartners.com/research/telco-economics-mobile-churn-rates-and-reduction-strategies/) for other mobile operators. Churn rate is very important because it is typically more expensive to obtain new customers than to retain existing customer. In order for SyriaTel to improve their churn rate, SyriaTel has tasked our team to help them predict which customers are likley to churn and provide actionable recommendations to mitigate churn.

## Data 

The dataset includes data of SyriaTel customer usage pattern and their churn status from [Kaggle](https://www.kaggle.com/becksddf/churn-in-telecoms-dataset). The data included ~3K customers with 20 columns.

Data includes:

The Target:
* churn

Features/Predictors:
* account length: the number of days the user maintains a phone plan account
* international plan: "yes" if the user has the international plan, otherwise "no"
* voice mail plan: "yes" if the user has the voice mail plan, otherwise "no"
* number of voice mail messages: the number of voice mail messages the user has sent
* total day minutes used: total number of minutes the user has been in calls during the day
* day calls made: total number of calls the user has completed during the day
* total day charge: total amount of money the user was charged by the Telecom company for calls made during the day 
* total evening minutes: total number of minutes the user has been in calls during the evening
* total evening calls: total number of calls the user has completed during the evening
* total evening charge: total amount of money the user was charged by the Telecom company for calls made during the evening
* total night minutes: total number of minutes the user has been in calls during the night
* total night calls: total number of calls the user has completed during the night
* total night charge: total amount of money the user was charged by the Telecom company for calls made during the night
* total international minutes used: total number of minutes the user has been in international calls
* total international calls made: total number of international calls the user has made
* total international charge: total amount of money the user was charged by the Telecom company for international calls made
* number customer service calls made: number of customer service calls the user has made

## Analysis

To set out on our objective of predicting which type of customers are most likely to churn, we began exploring the datatset's existing churn rate. We found that the current churn rate across all customers is 14.49%. After developing a firm understanding of the current churn rate across all customers, we then set our objective of identifying which features in a customer's phone plan most likely influences his or her churn rate. Upon identifying the key features that affect a customer's churn rate, we then wanted to directly address these features and create solutions that could decrease a customer's churn rate. Lastly, after identifying which key features help predict a customer's churn rate, we wanted to know which segment of customers to target our recommendations and solutions to reduce churn before deploying our recommendations across the entire nation. 

To build a classifier to predict whether a customer will end his or her phone plan with SyriaTel, we deployed a myriad of models to aid us in our prediction: 

* Logistic Regression Model
* K-Nearest Neighbors Model
* K-Nearest Neighbors Model with SMOTE
* Decision Tree Model
* Bagging Model with Decision Tree
* Random Forest Model
* XG Boost Model
* AdaBoost Model
* Gradient Boost Model
* Ensemble Voting Model

While it was important to assess all models based on the accuracy score, we have decided to emphasize the recall score as the main metric when assessing the prediction results of our models. As a telecommunications company with the aim of reducing customer churn, the recall score of each model was a more applicable metric as we aim to minimize the amount of false negative predictions. In the context of customer churn, we wanted to reduce the number of people that a model predicts as a customer who will not churn (hence stay with the phone company), when in actuality, the customer is likely to leave the phone company. Maximizing the recall score will ensure that the model does not miss out on any potential customers who are likely to churn and leave the phone company. 

## Results



## Conclusions

In conclusion, we have identified two of the most import key features when predicting a customer's churn rate in our best-performing Gradient Boost Model. The first key feature with a high influence on churn rate prediction is total charge. To better assess and apply this metric on our customers to decrease the churn rate, we looked into "total day minutes" as well as "charge per minute per day" as our anlaysis concluded that call minutes made during the daytime versus that of any other time segment had a bigger impact between customers who churn and those who do not churn. We implemented a recommendation to adjust a customer's charge per minute by looking at the 50% percentile of total day minutes to determine a cut off of 200 minutes as a threshold cut off. At this cut off at the 50% percentile, we then saw that 35 cent as a charge per daytiem minutes would be an appropriate fixed rate to implement at the cut off. Hence, we recommend SyriaTel to provide all customers who make 200 minutes of calls during the day with a fixed rate plan of 35 cents per minute for day calls. 

## Next Steps

## Repository Structure
