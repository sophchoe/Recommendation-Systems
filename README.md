# Recommendation-Systems
This folder contains two Jupyter Notebooks for Recommendation System projects based on MIT/ Great Learning Data Science course: Amazon Product Recommendation System and Book Review Recommentation System. For both of the projects, the following algorithms are explored:

## 1. Rank-based
  
Rank-based recommendation systems are designed to suggest items to users based on some form of ranking metric. These systems can be simple but effective, especially in scenarios where personalized recommendations are not necessary or when there is insufficient data to build user-specific profiles. These systems are straightforward to implement and understand and do not require complex algorithms or user data to start making recommendations. 
They are particularly useful for new users for whom the system has no previous interaction data (the cold start problem). They typically can be built based the following criteria:

#### Popularity: 
Items are ranked based on their popularity, measured through metrics such as sales numbers, views, or user ratings. The assumption is that items liked by many users are likely to be appreciated by a new user. Recommendations based on general popularity can appeal to a wide audience, making them suitable for public spaces or general-interest platforms.
#### Trending Items: 
Items that are currently trending or gaining rapid popularity are recommended. This can be particularly effective for content that is time-sensitive, like news articles or fashion.
#### Highest Rated: 
Items are ranked based on their average ratings or reviews. This approach assumes that higher-quality items will be universally appreciated.

This simple and powerful model has some drawbacks. The recommendations are not tailored to individual preferences, which may lead to less relevant suggestions for some users. Popular items get more exposure, which can perpetuate their popularity, potentially overshadowing quality or niche items that might be more relevant to specific users.

## 2. Collaborative Filtering
In implementing collaborative filtering, there are typically three implementation steps: similarity computation, neighborhood formation, and prediction and recommendation. The calculation of similarity between users or between items is performed, typically using metrics such as Pearson correlation, cosine similarity, or Euclidean distance. Once similarities are computed, the system forms a "neighborhood" of users/items for each target user/item, consisting of other users/items with the highest similarity scores. The size of this neighborhood can be fixed or variable, depending on the implementation. To recommend items to a target, the system aggregates the preferences (e.g., ratings) of the user/item's neighbors. This aggregation can be a weighted average where the weights are the similarity scores, ensuring that more similar users/items have a greater influence on the recommendation.

  ### - User-user similarity based
User-user similarity-based collaborative filtering is a technique used in recommendation systems to suggest items to a user based on the preferences of other users who have similar tastes or behaviors. This approach is rooted in the idea that users who agreed in the past tend to agree again in the future. 
  
Recommendations are persoanalizable, flexible and dyname. They are tailored to individual users based on their unique preferences and they can be applied to any domain where user preferences can be collected, such as movies, music, or shopping. The system dynamically and naturally adapts as users add more ratings or as new users join. However, New users or items with few interactions present a challenge, as there's insufficient data to compute reliable similarities. The computational complexity can become a problem with a large number of users and items, as calculating and updating similarities can be resource-intensive. In many systems, users interact with a small fraction of the total items, leading to sparse data matrices and making similarity calculations less reliable.

  ### - Item-item similarity based
  This method suggests items to users based on the similarity of items they have previously interacted with. It's particularly useful in environments where the number of items is much smaller than the number of users, or where user preference patterns are stable over time.

Item-item relationships tend to be more stable than user-user relationships because item characteristics change less frequently than user preferences.
Once item similarity is computed, generating recommendations can be more efficient, especially in systems with a vast number of users but relatively fewer items. This system is transparent because recommendations can be more easily explained by referring to the items that were used to find the similarity (e.g., "Because you watched A, you might like B").

However, new items with little to no interaction history can be challenging to recommend because there's insufficient data to determine their similarity to existing items. In cases where there's limited interaction data for many items, calculating accurate similarities can be difficult. For rapidly changing inventories, like fashion retail, maintaining up-to-date similarity measures can be challenging.
  
## 3. Matrix Factorization
Matrix factorization is a powerful technique used in recommendation systems to discover latent features underlying the interactions between users and items. This approach is particularly effective for making personalized recommendations and addressing the sparsity and scalability challenges of collaborative filtering. Matrix factorization methods decompose a large user-item interaction matrix into lower-dimensional matrices, revealing hidden patterns in the data. The following key concepts are essential in matrix factorization models:
#### User-Item Interaction Matrix: 
A large matrix where rows represent users, columns represent items, and the entries are the interactions (e.g., ratings, purchases) between users and items. This matrix is typically sparse, as not all users interact with all items.
#### Latent Features: 
These are the underlying attributes or characteristics that both users and items possess, which explain why certain users prefer certain items. Matrix factorization aims to identify these latent features.
#### Factorization: 
The process of decomposing the user-item matrix into two or more matrices that, when multiplied back together, approximate the original matrix. There are different decomposition methods: Singular Value Decomposition (SVD), Non-negative Matrix Factorization (NMF), and Alternating Least Squares (ALS). The most common decomposition produces a user feature matrix and an item feature matrix. The advantages of Matrix Factorizartion are dimensionality reduction, sparsity handling, personalization, and scalability.

For the two projects below, the following four algorithms are built for recommendation:
  - Rank-based using averages
  - User-user similarity-based collaborative filtering
  - Item-item similarity-based collaborative filtering
  - Model-based (matrix factorization) collaborative filtering

---------------------------------------------------------------------------------------
## **Project 1:**           Amazon Product Recommendation System
--------------------------------------------------------------------------------------- 

For this project, the task is building a recommendation system to recommend electronics products to Amazon customers based on their previous ratings for other products. We have a collection of labeled data of Amazon reviews of products. The goal is to extract meaningful insights from the data and build a recommendation system that helps in recommending products to online consumers.

The Amazon dataset contains the following attributes:

- **userId:** Every user identified with a unique id
- **productId:** Every product identified with a unique id
- **Rating:** The rating of the corresponding product by the corresponding user

In this case study, we built recommendation systems using four different algorithms:
  - **Rank-based using averages**: This was done by finding the average rating per product.
  - **User-user similarity-based collaborative filtering**: For a specific product, we can find potential customers to recommend the product by finding similar users to the user who have ranked the product high.
  - **Item-item similarity-based collaborative filtering**: For a specific user, we can find potential products the user may be interested in purchasing by finding similar products to the one the user has ranked high.
  - **Model-based (matrix factorization) collaborative filtering**: This is a user-item method using Singular Value Decomposition. It works by decomposing the user-item matrix into the product of two lower dimensionality rectangular matrices.

These are the observations from the experiments:
- Overall, the **optimized item-item method** has given the **best performance** in terms of the F1-Score (~0.869).
- **Optimized Matrix Factorization has the lowest RMSE (0.8808)**.
- **Optimized item-item filtering has the highest F1 score (0.869)**.




---------------------------------------------------------------------------------------
## **Project 2:**           Book Review Recommendation System
--------------------------------------------------------------------------------------- 
Book Recommendation Systems are used by the vast majority of E-commerce businesses such as Amazon, Barnes and Noble, Flipkart, Goodreads, and other online retailers to recommend books that customers may be tempted to buy based on their preferences. This feature can assist in increasing shopping value while reducing shopping time. Logical recommendations not only assist customers in making purchases but also increase total sales value.

The **ratings** dataset contains the following attributes: 
- **user-Id**: Unique ID for each user
- **ISBN**: International Standard Book Number. Books are identified by their respective ISBN
- **Book-rating**: Rating for each book expressed on a scale from 0-10

The **users** dataset contains the following attributes: 
- **user-Id**: Unique ID for each user
- **Location**: City, State, Country
- **Age**: Age when known and NAN when unknown

The **books** dataset contains the following attributes:
- **ISBN**: International Standard Book Number
- **Book-title**: Title of the book
- **Book-author**: Name of the author
- **Year-of-Publication**: Publication Year
- **Publisher**: Name of the publisher of the book
- **Image-Url-S**: Small image of the book (Amazon link)
- **Image-Url-M**: Medium size image of the book (Amazon link)
- **Image-Url-L**: Large size image of the book (Amazon link)

Observations:
- Matrix Factorization has lower RMSE (1.50) due to the reason that it assumes that both books and users are present in some low dimensional space describing their properties and recommend a book based on its proximity to the user in the latent space. 
