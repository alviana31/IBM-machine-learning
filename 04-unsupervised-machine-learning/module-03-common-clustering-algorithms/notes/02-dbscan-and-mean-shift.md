# DBSCAN and Mean Shift

## 1. DBSCAN

DBSCAN stands for Density-Based Spatial Clustering of Applications with Noise.

It is a density-based clustering algorithm that identifies clusters based on the density of data points in a particular region.

Unlike K-Means, DBSCAN does not require the number of clusters to be specified beforehand.

## 2. DBSCAN Parameters

DBSCAN uses two main parameters:

- **Epsilon (eps):** Defines the maximum distance between points for them to be considered neighbors.
- **MinPts (min_samples):** Defines the minimum number of points required within the epsilon neighborhood for a point to be considered a core point.

The selection of these parameters affects the clustering results.

## 3. Types of Points in DBSCAN

DBSCAN classifies data points into three main categories.

### A. Core Point

A core point has at least the minimum required number of points within its epsilon neighborhood.

### B. Border Point

A border point does not have enough neighboring points to be a core point, but it is located within the neighborhood of a core point.

### C. Noise Point

A noise point does not belong to any cluster based on the density requirements.

It is also commonly called an outlier.

## 4. How DBSCAN Works

The general process is:

1. Select a data point.
2. Identify its neighboring points within the epsilon distance.
3. Check whether the number of neighbors meets MinPts.
4. If the point is a core point, form or expand a cluster.
5. Continue connecting density-reachable points.
6. Mark points that do not belong to any cluster as noise.

## 5. Implementing DBSCAN

Scikit-learn provides the `DBSCAN` class.

Example:

```python
from sklearn.cluster import DBSCAN

model = DBSCAN(
    eps=0.5,
    min_samples=5
)

labels = model.fit_predict(X)

print(labels)
```

Explanation:

- `eps=0.5`: Sets the neighborhood radius.
- `min_samples=5`: Sets the minimum number of neighboring samples required for a core point.
- `fit_predict(X)`: Fits the model and returns cluster labels.

In Scikit-learn, a label of `-1` represents a noise point.

## 6. Mean Shift

Mean Shift is a density-based clustering algorithm that identifies clusters by locating areas with high concentrations of data points.

It works by repeatedly shifting candidate points toward regions with higher data density.

Unlike K-Means, Mean Shift does not require the number of clusters to be specified in advance.

## 7. How Mean Shift Works

The general process involves:

1. Select an initial point or candidate center.
2. Define a neighborhood around that point using a bandwidth.
3. Calculate the mean position of the neighboring data points.
4. Shift the candidate center toward the calculated mean.
5. Repeat until the center converges.
6. Group points that converge to the same or nearby density peaks.

The bandwidth determines the size of the neighborhood and can influence the number of clusters.

## 8. Implementing Mean Shift

Scikit-learn provides the `MeanShift` class.

Example:

```python
from sklearn.cluster import MeanShift

model = MeanShift(
    bandwidth=2
)

labels = model.fit_predict(X)

print(labels)
```

Explanation:

- `bandwidth=2`: Defines the neighborhood size used by the algorithm.
- `fit_predict(X)`: Fits the model and returns cluster labels.

The bandwidth should be selected based on the scale and distribution of the data.

## 9. DBSCAN vs. Mean Shift

| Aspect | DBSCAN | Mean Shift |
|---|---|---|
| Approach | Density-based | Density-based |
| Number of clusters | Not specified beforehand | Not specified beforehand |
| Main parameters | Epsilon and MinPts | Bandwidth |
| Noise detection | Explicitly identifies noise | Does not provide a dedicated noise label in the same way |
| Main idea | Connects dense regions | Moves points toward density peaks |

## 10. Key Takeaways

- DBSCAN identifies clusters based on point density.
- DBSCAN distinguishes core, border, and noise points.
- Mean Shift identifies clusters by locating density peaks.
- Both methods can determine clusters without specifying the number of clusters in advance.
- Parameter selection has an important influence on the results.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 3: DBSCAN and Mean Shift.