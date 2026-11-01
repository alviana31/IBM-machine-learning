# Selecting Clusters and Mixture of Gaussians

## 1. Selecting the Right Number of Clusters

One important step in K-Means is determining the appropriate number of clusters.

The value of K affects how the dataset is divided. If K is too small, different groups may be combined. If K is too large, the data may be divided into too many clusters.

One method used to help select K is the **Elbow Method**.

## 2. Elbow Method

The Elbow Method evaluates different values of K and observes how the clustering error changes.

The process generally involves:

1. Select a range of K values, for example from 1 to 10.
2. Train a K-Means model for each value of K.
3. Record the inertia for each model.
4. Plot the K values against their inertia.
5. Identify the point where the decrease in inertia starts to slow down significantly.

This point is called the elbow because the graph often resembles an arm with a bent elbow.

## 3. Inertia

Inertia measures the sum of squared distances between each data point and the centroid of its assigned cluster.

A lower inertia indicates that data points are closer to their assigned centroids.

However, inertia generally decreases as the number of clusters increases. Therefore, selecting K based only on the lowest inertia is not sufficient.

The Elbow Method helps identify a reasonable balance between the number of clusters and the compactness of the clusters.

## 4. Implementing the Elbow Method

Example using Python and Scikit-learn:

```python
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

inertia_values = []
cluster_range = range(1, 11)

for k in cluster_range:
    model = KMeans(
        n_clusters=k,
        init="k-means++",
        random_state=42,
        n_init=10
    )

    model.fit(X)
    inertia_values.append(model.inertia_)

plt.plot(cluster_range, inertia_values, marker="o")
plt.xlabel("Number of Clusters (K)")
plt.ylabel("Inertia")
plt.title("Elbow Method")
plt.show()
```

The graph can be used to observe where the reduction in inertia begins to slow down.

The selected K should also make sense for the dataset and the purpose of the analysis.

## 5. Mixture of Gaussians

Mixture of Gaussians is a probabilistic approach that represents data as a combination of multiple Gaussian distributions.

Each Gaussian component represents a possible group or cluster in the dataset.

Unlike the basic K-Means approach, which assigns each data point to one cluster, a Gaussian Mixture Model can represent the probability that a data point belongs to each component.

## 6. Gaussian Mixture Model (GMM)

A Gaussian Mixture Model assumes that the dataset is generated from a combination of several Gaussian distributions.

Each component has its own parameters, including:

- **Mean:** Represents the center of a Gaussian component.
- **Covariance:** Describes the spread and shape of the component.
- **Weight:** Represents the proportion of the dataset associated with that component.

The model estimates these parameters to describe the distribution of the data.

## 7. Implementing Gaussian Mixture Model

Scikit-learn provides the `GaussianMixture` class.

Example:

```python
from sklearn.mixture import GaussianMixture

# Create the Gaussian Mixture Model
gmm = GaussianMixture(
    n_components=3,
    random_state=42
)

# Fit the model
gmm.fit(X)

# Predict cluster assignments
labels = gmm.predict(X)

# Calculate membership probabilities
probabilities = gmm.predict_proba(X)
```

Explanation:

- `n_components=3`: Uses three Gaussian components.
- `fit(X)`: Estimates the model parameters from the data.
- `predict(X)`: Assigns each data point to its most likely component.
- `predict_proba(X)`: Returns the membership probabilities for each component.

## 8. K-Means vs. Gaussian Mixture Model

| Aspect | K-Means | Gaussian Mixture Model |
|---|---|---|
| Main approach | Distance-based clustering | Probabilistic modeling |
| Cluster representation | Centroid | Gaussian distribution |
| Assignment | One cluster per point | Probability for each component |
| Cluster shape | Generally compact clusters | Can represent different covariance structures |
| Main parameter | Number of clusters (K) | Number of components |

Both methods can be used to identify groups in unlabeled data, but they represent clusters differently.

## 9. Key Takeaways

- The number of clusters affects the result of K-Means.
- The Elbow Method helps identify a reasonable number of clusters.
- Inertia measures the sum of squared distances from data points to their assigned centroids.
- Mixture of Gaussians models data using multiple Gaussian distributions.
- Gaussian Mixture Models provide probabilistic cluster assignments.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 1: Selecting the Right Number of Clusters, Elbow Method, and Mixture of Gaussians.