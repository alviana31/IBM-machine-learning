# Multidimensional Scaling (MDS)

## 1. Definition

Multidimensional Scaling (MDS) is a family of dimensionality reduction algorithms used to represent data points in a lower-dimensional space while preserving their relationships.

Unlike PCA, which focuses on preserving variance, MDS focuses on preserving the distances or dissimilarities between data points.

MDS can also be used to visualize complex differences between observations in a lower-dimensional space.

## 2. How MDS Works

The general process involves:

1. Calculate or obtain the distances between data points.
2. Determine the desired number of dimensions.
3. Find a lower-dimensional representation of the data.
4. Optimize the representation to preserve the original distance relationships as closely as possible.

For example, data originally represented in three dimensions can be mapped into two dimensions while attempting to maintain the distances between observations.

## 3. Metric MDS

Metric MDS represents data points in a lower-dimensional embedding by minimizing a distance-based objective.

The goal is to preserve the original distances between data points as closely as possible.

## 4. Non-Metric MDS

Non-Metric MDS focuses on preserving the relative ordering of dissimilarities rather than requiring the exact original distances to be maintained.

It applies a function to the original distance values before minimizing the difference between the represented distances and the transformed dissimilarities.

## 5. Metric vs. Non-Metric MDS

| Aspect | Metric MDS | Non-Metric MDS |
|---|---|---|
| Main objective | Preserve distances | Preserve the ordering of dissimilarities |
| Distance relationship | Uses distance values | Uses transformed distance relationships |
| Optimization | Minimizes distance-based differences | Minimizes differences based on a transformed relationship |

## 6. Implementing MDS with Python

Scikit-learn provides the `MDS` class.

Example:

```python id="2d4r0c"
from sklearn.manifold import MDS

mds = MDS(
    n_components=2,
    dissimilarity="euclidean",
    random_state=0
)

X_mds = mds.fit_transform(X)
```

Explanation:

- `n_components=2`: Creates a two-dimensional representation.
- `dissimilarity="euclidean"`: Uses Euclidean distance to measure dissimilarity.
- `random_state=0`: Makes the random initialization reproducible.
- `fit_transform(X)`: Fits the model and transforms the data.

For precomputed distances and Non-Metric MDS, the configuration can be:

```python id="7x2l9n"
from sklearn.manifold import MDS

embedding = MDS(
    dissimilarity="precomputed",
    random_state=0,
    n_components=2,
    metric=False
)

X_embedding = embedding.fit_transform(distance_matrix)
```

Here, `distance_matrix` must contain the pairwise dissimilarities between observations.

## 7. PCA vs. MDS

| Aspect | PCA | MDS |
|---|---|---|
| Main objective | Preserve variance | Preserve distances |
| Approach | Linear transformation | Distance-based embedding |
| Input | Feature matrix | Feature matrix or dissimilarity matrix |
| Main use | Dimensionality reduction | Dimensionality reduction and visualization |

## 8. Other Manifold Learning Methods

The course also mentions other manifold learning techniques:

- **Isomap:** Uses nearest-neighbor relationships to represent the structure of data.
- **t-SNE:** Attempts to keep similar points close together and dissimilar points farther apart. It is commonly used for visualization.

Different methods can be tested to determine which one provides a useful lower-dimensional representation.

## 9. Key Takeaways

- MDS is used to represent data in a lower-dimensional space.
- MDS focuses on preserving distances between data points.
- Metric MDS works with distance values.
- Non-Metric MDS focuses on preserving the ordering of dissimilarities.
- PCA and MDS have different objectives.
- Isomap and t-SNE are other examples of manifold learning methods.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 5: Multidimensional Scaling.