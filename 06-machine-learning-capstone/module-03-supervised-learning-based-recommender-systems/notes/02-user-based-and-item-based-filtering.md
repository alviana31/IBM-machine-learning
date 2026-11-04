# User-Based and Item-Based Filtering

## 1. User-Based Filtering

User-based filtering identifies users who have similar preferences to the active user.

The recommendation is generated using the ratings of users within the same neighborhood.

### Workflow

1. Identify the active user.
2. Compare the active user's ratings with other users.
3. Calculate similarity using commonly rated items.
4. Select users with similar rating patterns.
5. Multiply similarity weights by their ratings.
6. Aggregate and normalize the weighted ratings.
7. Rank the candidate items.

### Example

Suppose User 1 and User 3 both like Item 3 and Item 4.

Because they share similar preferences, Item 1, which is positively rated by User 1, can be recommended to User 3.

## 2. Item-Based Filtering

Item-based filtering identifies items that have similar rating patterns among users.

The system builds neighborhoods of similar items based on user behavior.

### Workflow

1. Identify items that users have rated.
2. Compare rating patterns between items.
3. Identify items with similar user rating behavior.
4. Find items related to those already liked by the active user.
5. Recommend related items.

### Example

If Item 1 and Item 3 are positively rated by User 1 and User 2, they can be considered similar items.

If User 3 likes Item 3, the system may recommend Item 1.

## 3. Comparison

| Aspect | User-Based | Item-Based |
|---|---|---|
| Main Focus | Similar users | Similar items |
| Similarity | Between users | Between items |
| Recommendation Basis | Ratings from similar users | Ratings of similar items |
| Example | Recommend what similar users liked | Recommend items similar in rating behavior to liked items |

## 4. Challenges of Collaborative Filtering

Collaborative filtering has several challenges.

### 4.1 Data Sparsity

Data sparsity occurs when a large dataset contains many users, but each user rates only a limited number of items.

As a result, the user-item matrix may contain insufficient ratings to calculate reliable recommendations.

The system may be unable to predict an item's rating when too few users have rated it.

### 4.2 Cold Start Problem

The cold start problem occurs when the system has insufficient information about a new user or item.

It can happen in two situations:

- **New User:** The user has not provided enough ratings or interaction history to build a profile.
- **New Item:** The item has not received any ratings, making it difficult to identify relationships with other items.

### 4.3 Scalability

Scalability becomes a challenge as the number of users, items, and ratings increases.

Similarity calculations can become more demanding as the dataset grows, potentially reducing system performance.

## 5. Possible Solution

The course material mentions hybrid recommender systems as one possible approach to address challenges in collaborative filtering.

A hybrid system combines different recommendation mechanisms.

The detailed implementation of these solutions is outside the scope of this course module.

## 6. Key Takeaways

- User-based filtering recommends items using similar users.
- Item-based filtering recommends items using similar item rating patterns.
- Data sparsity occurs when user-item ratings are insufficient.
- Cold start occurs when a new user or item has little or no interaction history.
- Scalability becomes challenging as the dataset grows.
- Hybrid recommender systems can combine multiple recommendation approaches.