# Machine-Learning-CapStone-Project
### Kaggle compeition
### Zillow Prize: Zillow’s Home Value Prediction (Zestimate)
### Lei Pan 

## Project Overview
* Zillow created “Zestimate” which gives customers a lot of information about homes and housing markets at no cost by using publicly available data. 
* 7.5 million statistical and machine learning models that analyze hundreds of data points on each property are used by Zillow to create and improve “Zestimate”. They improved median margin of error from 14% to 5%. Zillow announced a Kaggle competition to improve the accuracy of “Zestimate” even further.
* Zillow competition has two rounds. The first round is to build a model to predict Zillow residual error. The final round is to build a home evaluation algorithm from ground up using all external data. My project will focus on the first round of the competition. The goal of capstone project is to build a model to improve Zillow residual error.
* This is a very typical supervised machine learning problem, because supervised learning algorithms learns and analyzes labeled training data and then generates function to predict output. Zillow gave the datasets of log error between Zestimate price and actual price for both 2016 and 2017 which are labeled data as well as Zillow asked for a prediction for log error. Similar machine learning tasks are weather apps predict the temperature for a given time and spamming emails prediction based on prior spamming information.

## Problem Statement
* A machine learning computer program is said to learn from experience E with respect to some class of task T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E. In this capstone project: 
* P is Mean absolute error of predicted log error and actual log error.
* T is The log error prediction task.
* E is The process of the algorithm examining a large amount of historical data of log error.
* This is the link to all the datasets I am using: https://www.kaggle.com/c/zillow-prize-1/data Train_2016.csv,properties_2016.csv,Train_2017.csv,properties_2017.csv 

## Metrics
* Models are evaluated on Mean Absolute Error between the predicted log error and the actual log error. The log error is logerror=log(Zestimate)−log(SalePrice)
* If I can build a model with a MAE that’s less than the MAE of base model, then the model passes evaluation.The reason I chose this evaluation metrics is that 1) this is provided by Zillow to evaluate actual competition. 2)Since every Zillow competition participant uses and publishes this evaluation metrics, I can compare my MAE with all the MAEs for Zillow competition participants’ models to get a sense how well I am doing among all the professionals around the world.


