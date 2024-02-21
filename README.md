# Recommendation-Systems
Recommendation system projects based on MIT Data Science course. For both projects, the exploration of the following algorithms is done:
- ** Rank-based
  
Rank-based recommendation systems are designed to suggest items to users based on some form of ranking metric. These systems can be simple but effective, especially in scenarios where personalized recommendations are not necessary or when there is insufficient data to build user-specific profiles. Here's an overview of how rank-based recommendation systems work and their key characteristics:

*** Popularity: Items are ranked based on their popularity, measured through metrics such as sales numbers, views, or user ratings. The assumption is that items liked by many users are likely to be appreciated by a new user.
*** Trending Items: Items that are currently trending or gaining rapid popularity are recommended. This can be particularly effective for content that is time-sensitive, like news articles or fashion.
*** Highest Rated: Items are ranked based on their average ratings or reviews. This approach assumes that higher-quality items will be universally appreciated.

These systems are straightforward to implement and understand. They don't require complex algorithms or user data to start making recommendations. 
Recommendations based on general popularity can appeal to a wide audience, making them suitable for public spaces or general-interest platforms.
They are particularly useful for new users for whom the system has no previous interaction data (the cold start problem). 

However, this simple and powerful model has some drawbacks. The recommendations are not tailored to individual preferences, which may lead to less relevant suggestions for some users. Popular items get more exposure, which can perpetuate their popularity, potentially overshadowing quality or niche items that might be more relevant to specific users.

- ** Collaborative Filtering
  - *** User-user similarity based
    User-user similarity-based collaborative filtering is a technique used in recommendation systems to suggest items to a user based on the preferences of other users who have similar tastes or behaviors. This approach is rooted in the idea that users who agreed in the past tend to agree again in the future. Here's an overview of how this system works, its key characteristics, and the steps involved in building one:
    **** 1. Similarity Computation: The cornerstone of user-user collaborative filtering is the calculation of similarity between users. This is typically done using metrics such as Pearson correlation, cosine similarity, or Euclidean distance. These metrics compare users' ratings or interactions with items to identify users with similar preferences.
**** 2. Neighborhood Formation: Once similarities are computed, the system forms a "neighborhood" of users for each target user, consisting of other users with the highest similarity scores. The size of this neighborhood can be fixed or variable, depending on the implementation.
**** 3. Prediction and Recommendation: To recommend items to a target user, the system aggregates the preferences (e.g., ratings) of the user's neighbors. This aggregation can be a weighted average where the weights are the similarity scores, ensuring that more similar users have a greater influence on the recommendation.

  - *** Item-item similarity based
- ** Matrix Factorization

## Amazon Product Recommendation System

The task is building a recommendation system to recommend electronics products to Amazon customers based on their previous ratings for other products. We have a collection of labeled data of Amazon reviews of products. The goal is to extract meaningful insights from the data and build a recommendation system that helps in recommending products to online consumers.

-----------------------------
## **Dataset:**
-----------------------------

The Amazon dataset contains the following attributes:

- **userId:** Every user identified with a unique id
- **productId:** Every product identified with a unique id
- **Rating:** The rating of the corresponding product by the corresponding user
- **timestamp:** Time of the rating. We **will not use this column** to solve the current problem

Exploratory Data Analysis
