# Recommender System

This is the second big project that I've worked on during the course of learning ML.

Dataset used is MovieLens 100K latest. I've only used the part of the data which has the rating in it as my intention was to build a pure collaborative filtering recommendation engine. I haven't used any content based data because it would've hampered my intention of doing this project. If you're wondering, content based data would furthur enhance my recommender system and it's done using a mixture of collaborative filtering and content based information in the real world.

In this project I've built three models for recommending movies 
1. Regression Model
2. User-user similarity model
3. Matrix factorization model

**METRIC USED: RMSE and MAE**

[Nb]: Before building any model I did some preliminary check and simple data analysis to see whether the data was okay or not. Whether it needed some sort of data-cleaning or not. Fortunately all was alright. In the data I didn't have any movies whose ratings had a high variance.(high variance causes unpredicatbility)

## Regression Model
In the Regression based model I've blindly made a regressor just to set a benchmark of the performace. With hyperparameter tuning. 

**RMSE: 1.066698503735705
MAE: 0.8563265025436632 **

This was expected.

After this I did some feature engineering where I added 4 different features
* Mean ratings that the movie got
* Std-dev of the ratings that the movie got
* Mean ratings that the user has given
* Std-dev of the ratings that the user has given

Surprisingly there was a considerable amount of decrease in the error metric

**RMSE: 0.8337655216879091
MAE: 0.6387381172964315**

I was very happy with this result as it proves that little bit of good feature engineering goes a long way.
