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

**RMSE: 1.066698503735705 <br>
MAE: 0.8563265025436632**

This was expected.

After this I did some feature engineering where I added 4 different features
* Mean ratings that the movie got
* Std-dev of the ratings that the movie got
* Mean ratings that the user has given
* Std-dev of the ratings that the user has given

Surprisingly there was a considerable amount of decrease in the error metric

**RMSE: 0.8337655216879091 <br>
MAE: 0.6387381172964315**

I was very happy with this result as it proves that little bit of good feature engineering goes a long way.

## User-User similarity model
This another way of doing collaborative filtering recommender system. I implemented user-user similarity model directly from scratch and without using any help of machine learning libraries.

Before implementing the model I've gotten rid of those users who haven't rated atleast 10 movies and also gotten rid of those movies which haven't been rated atleast 10 times. 

After some cleaning I've picked a querry point and I found out users who have atleast 10 common movies with the querry user and this 10 common movies must have the querry movie in common too.

After finding such users, I had to filter most-similar users from the list of users. I determined the most similar users using the euclidean distance between the querry point and the list of users. Lesser the distance, more similar are the users. 

After getting the most similar users, I've declared the mean of the rating of the movie given by the most similar users as my prediction. 

**RMSE: 0.9421296447411392 <br>
MAE: 0.723495951243854**

Even though I didn't get an improvement since my last model, I was pretty happy because this is working pretty well for a self implemented algorithm.

##Simple Matrix factorization model
This is the last model I had implemented. I had used a library called spotlight. In the future I want to implement Matrix factorization model completely from scratch

**RMSE: 1.003307580947876**

The result was not what I had expected. 

The biggest takeaway from this should be, fancy models doesn't always mean better results. Sometimes the simplest models perform the best. It all depends on the data.
