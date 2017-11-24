## Machine Learning Engineer Nanodegree - Capstone Project
### Kaggle compeition - Zillow Prize: Zillow’s Home Value Prediction (Zestimate)
### Lei Pan 
### Set up those libraries to run the project
* Install Python 3, sklearn, numpy, pandas, matplotlib, and seaborn
* Install the lastest lightGBM. Follow instruction here:https://lightgbm.readthedocs.io/en/latest/Installation-Guide.html
* Install the lastest XGBoost. Follow instructuion here:http://xgboost.readthedocs.io/en/latest/build.html
* Make sure you have all the datasets downloaded - train_2016.csv, properties_2016.csv, train_2017.csv, properties_2017.csv, and zillow_data_dictionary.xlsx. You can find all the data here:https://www.kaggle.com/c/zillow-prize-1/data. It's called train_2016_v2.csv on kaggle site. Please change the name to train_2016.csv when running Jupyter notebook.
* Please put all your datasets inside dataset folder (I put a placeholder file there), otherwise Jupyter notebook won't be able to find those datasets.

### Project Overview
* Zillow created “Zestimate” which gives customers a lot of information about homes and housing markets at no cost by using publicly available data. 
* 7.5 million statistical and machine learning models that analyze hundreds of data points on each property are used by Zillow to create and improve “Zestimate”. They improved median margin of error from 14% to 5%. Zillow announced a Kaggle competition to improve the accuracy of “Zestimate” even further.
* Zillow competition has two rounds. The first round is to build a model to predict Zillow residual error. The final round is to build a home evaluation algorithm from ground up using all external data. My project will focus on the first round of the competition. The goal of capstone project is to build a model to improve Zillow residual error.
* This is a very typical supervised machine learning problem, because supervised learning algorithms learns and analyzes labeled training data and then generates function to predict output. Zillow gave the datasets of log error between Zestimate price and actual price for both 2016 and 2017 which are labeled data as well as Zillow asked for a prediction for log error. Similar machine learning tasks are weather apps predict the temperature for a given time and spamming emails prediction based on prior spamming information.

### Problem Statement
* A machine learning computer program is said to learn from experience E with respect to some class of task T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E. In this capstone project: 
* P is Mean absolute error of predicted log error and actual log error.
* T is The log error prediction task.
* E is The process of the algorithm examining a large amount of historical data of log error.
* This is the link to all the datasets I am using: https://www.kaggle.com/c/zillow-prize-1/data Train_2016.csv,properties_2016.csv,Train_2017.csv,properties_2017.csv 

### Metrics
* Models are evaluated on Mean Absolute Error between the predicted log error and the actual log error. The log error is logerror=log(Zestimate)−log(SalePrice)
* If I can build a model with a MAE that’s less than the MAE of base model, then the model passes evaluation.The reason I chose this evaluation metrics is that 1) this is provided by Zillow to evaluate actual competition. 2)Since every Zillow competition participant uses and publishes this evaluation metrics, I can compare my MAE with all the MAEs for Zillow competition participants’ models to get a sense how well I am doing among all the professionals around the world.

### Solution
* First, exploratory data visualization was performed on couple aspects of the problem such as input dataset, missing values, non numerical data, distribution of targeted values, and coefficient of features with targeted values. 
* After understanding dataset, data preprocessing was taken out to make sure training dataset was well prepared and valid. 
* Then benchmark model was implemented with some optimal parameters and cross validation as well as tested it out with testing data against performance metric MAE. 
* After benchmark model implementation, cross validation was improved and parameters were tuned to generate the second model - lightGBM model. lightGBM model was trained and tested out against MAE. It got a better MAE. XGBoost model was implemented and tuned after that. 
* Eventually, a meta model - the combination of lightGBM and XGBoost models was born. The final combined model was tested out against 3 different testing datasets to check its consistency. The final model got the best MAE among all the models and it performed pretty consistent across all different test datasets.
* MAE for the final model is 0.06939.
