# Predict Future Sales


This project documents my participation on Kaggle's competition "Predict Future Sales". In this competiton, we are provided with daily historical data for stores in Russia. 

The data consists of more than 20 thousand unique items, for 60 different stores. The objective is to predict the total sales for every product and stores in the next month. 

This competition is interesting because it uses a relativey large time series dataset (more than 200k rows).


### Evolution of Approaches


1. Naive approach. Since the test set contains one-month ahead data, the benchmark approach is to use sales from the last month in the dataset. This achieves a performance of 1.1677 (RMSE) on the public leaderboard.
2. Mean encoded features and some lags. By adding lags of mean encoded features (sales by month-shop, month-item and month-shop-item aggregations) and using a linear regression model with no hyperparameter tuning improves the score to 1.0083 on the public leaderboard.
3. Stacking of linear regression and lightgbm model with the same set of features as the previous approach: 0.9985 on the public leaderboard.
4. Adding new features to the previous approach: information from text data (city name, item category and subcategory) and more mean-encoded features. This improves the score to 0.9665.
