# Collaborative Filtering

## 1. Introduction

Collaborative Filtering is a recommender system technique that uses relationships between users and their interests to recommend items.

The main idea is that users with similar preferences may be interested in similar items.

The system analyzes user behavior, such as ratings, viewing history, and purchasing choices, to identify these relationships.

## 2. Types of Collaborative Filtering

Collaborative filtering has two main approaches:

- User-Based Collaborative Filtering
- Item-Based Collaborative Filtering

### 2.1 User-Based Collaborative Filtering

User-based collaborative filtering recommends items by identifying users with similar interests.

The system:

1. Selects an active user who needs recommendations.
2. Finds other users with similar rating patterns.
3. Calculates similarity between the active user and other users.
4. Uses ratings from similar users to estimate the active user's possible ratings for unseen items.
5. Ranks the candidate items and generates recommendations.

For example, if two users have similar movie preferences, a movie highly rated by one user may be recommended to the other.

### 2.2 Item-Based Collaborative Filtering

Item-based collaborative filtering recommends items based on relationships between items.

The system identifies items that receive similar ratings or are positively rated by similar groups of users.

For example, if a user likes one movie, the system may recommend another movie that has a similar rating pattern among users.

Unlike content-based filtering, item-based collaborative filtering does not rely on item characteristics or genres. It uses user rating behavior to determine item similarity.

## 3. Similarity Measurements

The system needs to calculate similarity to identify related users or items.

Some techniques mentioned in the course material include:

### Euclidean Distance

Measures the distance between two data points. It can be used to evaluate how close two users or items are based on their rating values.

### Pearson Correlation

Measures the correlation between two sets of values.

### Cosine Similarity

Measures the similarity between two vectors based on the angle between them.

These techniques can be used to determine similarity between users or items.

## 4. Weighted Rating Matrix

After calculating similarity between users, the system uses similarity values as weights for their ratings.

Users with higher similarity to the active user contribute more strongly to the predicted ratings.

The weighted ratings are then aggregated to estimate the active user's possible ratings for candidate items.

## 5. Normalizing Predicted Ratings

Different candidate items may have ratings from different numbers of users.

To make the results comparable, the weighted rating values are divided by the sum of the similarity weights of the users who rated the item.

The resulting values represent the predicted ratings for the active user.

## 6. Recommendation Ranking

After calculating predicted ratings, the system ranks candidate items.

Items with higher predicted ratings are considered more suitable for recommendation.

## 7. Key Takeaways

- Collaborative filtering uses user behavior and rating patterns.
- User-based filtering finds users with similar preferences.
- Item-based filtering finds relationships between items based on user ratings.
- Similarity can be measured using Euclidean Distance, Pearson Correlation, and Cosine Similarity.
- Similarity weights are used to calculate predicted ratings.
- Candidate items can be ranked based on their predicted ratings.