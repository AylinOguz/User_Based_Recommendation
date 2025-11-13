# User Based Recommendation
![image](https://github.com/AylinOguz/User_Based_Recommendation/blob/main/user_based.png?raw=true)

User-Based Movie Recommendation System

This project implements a User-Based Collaborative Filtering (UBCF) movie recommendation system using the MovieLens dataset. The system provides personalized movie recommendations by analyzing users with similar viewing behavior.


## Project Workflow

- Data Preparation

Merge movies.csv and ratings.csv on movieId.

Remove movies with fewer than 1000 ratings to reduce noise.

Create a User × Movie matrix, where rows represent users, columns represent movies, and values are ratings.

- Determine Movies Watched by the Target User

Randomly select a target user.

Extract all movies that the user has rated.

- Identify Users with Similar Viewing Behavior

Filter other users based on overlap with target user’s watched movies.

Remove users who have rated too few of the same movies (to avoid unreliable similarity).

Calculate Pearson correlation between the target user and other users to find the most similar users.

- Calculate Weighted Recommendation Scores

Multiply ratings of similar users by their correlation with the target user:

weighted_rating = correlation_with_target_user * rating


Aggregate weighted ratings for each movie.

Recommend movies with weighted ratings above a defined threshold (e.g., 3.5 or 4.0).

- Return Recommended Movies

Merge recommended movie IDs with the movies dataset to get movie titles.

Output a ranked list of personalized movie recommendations.


## Key Features

- User-Based Collaborative Filtering: Recommendations are based on other users with similar ratings.

- Weighted Scores: Ratings from users with higher similarity contribute more to recommendations.

- Filtering: Users and movies with too few ratings are excluded to improve reliability.

- Reusable Functions: create_user_movie_df() and user_based_recommender() allow easy deployment for any target user.
