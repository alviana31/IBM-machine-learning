# K-Means Clustering

## 1. Definition

K-Means is an unsupervised machine learning algorithm used to divide data into a specified number of clusters.

The algorithm groups data points based on their distance from the center of each cluster, called a centroid.

The value of K represents the number of clusters that the algorithm will create.

For example, if K = 3, the algorithm will attempt to divide the dataset into three groups.

## 2. How K-Means Works

K-Means generally follows these steps:

1. **Determine the number of clusters:** Select the value of K.
2. **Initialize centroids:** Choose initial centroid positions.
3. **Assign data points:** Calculate the distance between each data point and the centroids. Assign each point to its nearest centroid.
4. **Update centroids:** Calculate the mean position of the data points in each cluster.
5. **Repeat the process:** Reassign points and update centroids until the assignments no longer change or the algorithm reaches its stopping condition.

## 3. Centroid

A centroid represents the center of a cluster.

The centroid is calculated using the mean of the feature values of all data points assigned to that cluster.

For a dataset with two features, the centroid can be represented as:

\[
C = \left(\frac{\sum x_i}{n}, \frac{\sum y_i}{n}\right)
\]

Where:

- \(x_i\) and \(y_i\) are feature values.
- \(n\) is the number of data points in the cluster.

## 4. K-Means Initialization

Initialization determines the starting positions of the centroids.

The initial centroid positions can affect the final clustering results.

One initialization method discussed in this module is **K-Means++**.

K-Means++ selects initial centroids with the aim of spreading them apart. It helps reduce the chance of selecting initial centroids that are too close to one another.

## 5. Convergence

K-Means repeats the assignment and centroid update steps until the algorithm converges.

Convergence occurs when the cluster assignments stop changing or another stopping condition is reached.

## 6. Implementing K-Means with Python

The Scikit-learn library provides the `KMeans` class through `sklearn.cluster`.

Example:

```python
from sklearn.cluster import KMeans

# Create the K-Means model
kmeans = KMeans(
    n_clusters=3,
    init="k-means++",
    random_state=42,
    n_init=10
)

# Train the model
kmeans.fit(X)

# Predict cluster assignments
labels = kmeans.predict(X)

# Display cluster centers
print(kmeans.cluster_centers_)
```

Explanation:

- `n_clusters=3`: Creates three clusters.
- `init="k-means++"`: Uses K-Means++ for centroid initialization.
- `random_state=42`: Makes the initialization reproducible.
- `n_init=10`: Runs the algorithm with multiple initializations.
- `fit(X)`: Fits the model to the dataset.
- `predict(X)`: Assigns data points to clusters.
- `cluster_centers_`: Returns the coordinates of the cluster centroids.

## 7. Important Considerations

- K-Means requires the number of clusters to be specified.
- The initial centroid positions can influence the result.
- Feature scaling may be important when features have different ranges.
- K-Means uses distance calculations, so the choice of features affects the clustering result.
- The algorithm works best when the clusters are reasonably compact and separated.

## 8. Key Takeaways

- K-Means groups data points into K clusters.
- Each cluster is represented by a centroid.
- The algorithm repeatedly assigns data points and updates centroids.
- K-Means++ is one method for initializing centroids.
- Scikit-learn can be used to implement K-Means in Python.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 1: K-Means Clustering.