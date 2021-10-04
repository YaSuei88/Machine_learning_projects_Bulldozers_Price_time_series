# Predicting the Sale Price of Bulldozers - Project Overview

This is my learning project when taking Machine Learning 0-Master course on Udemy. The goal is to predict the sale price of bulldozer, and this is a time-series related  
project. The original project is from Kaggle.

## 1. Problem definition
How well can we predict the future sale price of a bulldozer, giving the characterics and the previous examples of how much similar bulldozers have been sold for?

## 2. Data
The data is downloaded from the Kaggle Bluebook for Bulldozers competition: https://www.kaggle.com/c/bluebook-for-bulldozers/data

View and download the benchmark code from Github:
https://github.com/benhamner/BluebookForBulldozers/tree/master/Benchmark


The data  is split into three parts:

1. Train.csv is the training set, which contains data through the end of 2011.

2. Valid.csv is the validation set, which contains data from January 1, 2012 - April 30, 2012 You make predictions on this set throughout the majority of the competition. Your score on this set is used to create the public leaderboard.

3. Test.csv is the test set, which won't be released until the last week of the competition. It contains data from May 1, 2012 - November 2012. Your score on the test set determines your final rank for the competition.

## 3. Code and Resource Used
Python version: 3.7
Packages:  pandas, numpy, matplotlib.pyplot, sklearn, catboost

## 4. EDA
I looked at the distributions of the data and values counts for various categorical variables. Below are a few highlights from  pivot tables:

![image](https://user-images.githubusercontent.com/70978272/133983825-f60e7ec8-34e2-46b3-897a-63eed1ee8787.png)


## 5. Data Cleaning
After download the data from Kaggle, I cleaned the data so it could be used by our models. This is what I have done to clean the data:

* Parsing Dates: using parse_date parameter in pandas to convert the date column, so I can sort the data by sale date.
* Make a copy of the original data frame, so we can paly around with it.
* Add datetime parameters for saledate column.
* Convert astring into category.
* Filling missing nummerical values.
* Filling and tuning categorical variables into numbers

## 6. Modelling
I used two models to predcit the price: **Random Forest Regressor** and **catboost**. In both models, I used RandomSearchCV to find the best paramters for each model to fine tune
the models.


## 7. Evaluataion
The evaluation metric for this competition is the RMSLE (root mean squared log error) between the actual and predicted auction prices.

For more the evaluation of the this project, please check:
https://www.kaggle.com/c/bluebook-for-bulldozers/overview/evaluation

## 8. Result
Random Forest regressor model performed slightly better than Catboost, but there is no significant difference between the two models that I used in this project.

Random Forest regressor - Valid RMSLE': 0.25346274312057565 (with the best hyperparameters found via  RandomSearchCV 
Catboost: - Valid RMSLE: ': 0.2545226666113938

![image](https://user-images.githubusercontent.com/70978272/135902797-88893a98-b009-494b-8e60-812b0abd79d8.png)


