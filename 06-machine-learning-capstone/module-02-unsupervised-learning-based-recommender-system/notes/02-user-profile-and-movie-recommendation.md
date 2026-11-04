# User Profile and Movie Recommendation

## 1. Building a User Profile

A user profile represents the user's interests based on ratings given to previously watched movies.

In the course example, the system uses:

- Input User Ratings
- Movie Feature Set Matrix

The ratings represent the user's evaluation of watched movies, while the feature matrix represents the genres of those movies.

## 2. One-Hot Encoding

One-hot encoding is used to represent movie genres as numerical features.

Each genre is represented by a separate feature.

For example:

| Movie | Adventure | Super Hero | Comedy | Science Fiction |
|---|---:|---:|---:|---:|
| Movie A | 1 | 1 | 0 | 0 |
| Movie B | 1 | 1 | 1 | 1 |
| Movie C | 0 | 0 | 1 | 1 |

A value of 1 indicates that the movie belongs to the genre, while 0 indicates that it does not.

## 3. Weighted Genre Matrix

The user's ratings are combined with the movie feature set matrix.

The result is called the Weighted Genre Matrix.

It represents the user's interests in different genres based on the movies they have watched and rated.

The weighted genre matrix helps identify which genres are more important to the user.

## 4. Creating the User Profile

The user profile is created by aggregating the weighted genre values and normalizing them.

The resulting profile represents the user's interests across different genres.

For example, the profile may indicate that a user prefers superhero movies more than other genres.

## 5. Calculating Candidate Movie Scores

After creating the user profile, the system evaluates movies that the user has not watched.

The candidate movies are also encoded using one-hot encoding.

The system then combines the user profile with the candidate movie feature matrix to calculate weighted movie scores.

These scores represent the user's possible interest in each candidate movie.

## 6. Ranking Recommendations

The system aggregates the weighted scores for each candidate movie.

The resulting scores are used to rank the candidate movies.

The movie with the highest score becomes the most suitable recommendation according to the user's profile.

The course example identifies *The Hitchhiker's Guide to the Galaxy* as the candidate with the highest score.

## 7. Overall Workflow

```text
User Ratings
     |
     v
Movie Feature Set Matrix
     |
     v
One-Hot Encoding
     |
     v
Weighted Genre Matrix
     |
     v
User Profile
     |
     v
Candidate Movie Features
     |
     v
Weighted Movie Scores
     |
     v
Recommendation Ranking
     |
     v
Recommended Movie
```

## 8. Key Takeaways

- User ratings represent preferences for previously watched movies.
- One-hot encoding converts movie genres into numerical features.
- The weighted genre matrix represents the user's interest in different genres.
- The user profile is created by aggregating and normalizing weighted genre values.
- Candidate movies are evaluated using the user profile.
- The highest-scoring candidate is ranked as the recommended movie.