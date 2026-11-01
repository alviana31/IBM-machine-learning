# Hierarchical Agglomerative Clustering

## 1. Definition

Hierarchical Agglomerative Clustering is an unsupervised learning algorithm that groups data points through a hierarchical process.

The algorithm starts by treating each data point as an individual cluster. It then repeatedly combines the closest clusters until the desired number of clusters is reached or all points belong to one cluster.

This approach produces a hierarchy of clusters that can be represented using a dendrogram.

## 2. How It Works

The general process involves:

1. Start with each data point as an individual cluster.
2. Calculate the distances between clusters.
3. Identify the two closest clusters.
4. Merge those clusters into one.
5. Recalculate the distances between the updated clusters.
6. Repeat until the stopping condition is reached.

## 3. Hierarchical Linkage Types

Linkage determines how the distance between two clusters is calculated.

### A. Single Linkage

Single linkage measures the minimum distance between any two points from different clusters.

It focuses on the closest pair of observations between clusters.

### B. Complete Linkage

Complete linkage measures the maximum distance between any two points from different clusters.

It focuses on the farthest pair of observations between clusters.

### C. Average Linkage

Average linkage calculates the average distance between all pairs of points from two different clusters.

### D. Ward Linkage

Ward linkage merges clusters based on the increase in within-cluster variance.

It aims to minimize the increase in the total within-cluster sum of squares after each merge.

## 4. Comparison of Linkage Types

| Linkage | Distance Calculation |
|---|---|
| Single | Minimum distance |
| Complete | Maximum distance |
| Average | Average distance |
| Ward | Increase in within-cluster variance |

## 5. Implementing Hierarchical Clustering

Scikit-learn provides `AgglomerativeClustering` for implementing this algorithm.

Example:

```python
from sklearn.cluster import AgglomerativeClustering

model = AgglomerativeClustering(
    n_clusters=3,
    linkage="ward"
)

labels = model.fit_predict(X)

print(labels)
```

Explanation:

- `n_clusters=3`: Specifies three clusters.
- `linkage="ward"`: Uses Ward linkage.
- `fit_predict(X)`: Fits the clustering model and returns cluster labels.

## 6. Advantages and Limitations

**Advantages:**

- Does not require random centroid initialization.
- Provides a hierarchical view of the data.
- Different linkage methods can be selected.

**Limitations:**

- Can be computationally expensive for large datasets.
- Results can depend on the selected linkage method.
- Merging decisions are generally not reversed during the algorithm.

## 7. Key Takeaways

- Hierarchical Agglomerative Clustering builds clusters through repeated merging.
- Each data point initially forms its own cluster.
- Linkage determines how distances between clusters are calculated.
- Single, complete, average, and Ward are common linkage methods.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 3: Hierarchical Agglomerative Clustering.