# Principal Component Analysis (PCA)

## 1. Definition

Principal Component Analysis (PCA) is a dimensionality reduction technique that transforms the original features into a new set of features called principal components.

These components are created through linear combinations of the original features.

The purpose is to represent the dataset using fewer dimensions while preserving as much of the original data variance as possible.

## 2. Principal Components

Principal components are new feature vectors produced by PCA.

Each principal component has the following characteristics:

- It is a linear combination of the original features.
- Principal components are orthogonal to one another.
- Each component explains a certain amount of variance in the original dataset.
- Components are ordered according to the amount of variance they explain.

The first principal component explains the largest amount of variance.

The second principal component explains the largest amount of remaining variance while being orthogonal to the first component.

The process continues for the following components.

## 3. Explained Variance

Explained variance measures how much of the original data variance is retained by a principal component.

The explained variance ratio indicates the proportion of total variance represented by each component.

For example, if the first two components explain 85% of the total variance, then those two components preserve approximately 85% of the variation in the original dataset.

The number of components can be selected based on how much variance needs to be retained.

## 4. General PCA Process

The general steps include:

1. Prepare the dataset.
2. Scale the features when their ranges differ significantly.
3. Fit PCA to the data.
4. Examine the explained variance.
5. Select the desired number of components.
6. Transform the original data into the reduced feature space.

## 5. Implementing PCA with Python

Scikit-learn provides the `PCA` class in `sklearn.decomposition`.

Example:

```python
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA

# Standardize the data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Apply PCA
pca = PCA(n_components=2)
X_pca = pca.fit_transform(X_scaled)

# Check explained variance
print(pca.explained_variance_ratio_)

# Check total explained variance
print(pca.explained_variance_ratio_.sum())
```

Explanation:

- `StandardScaler()`: Standardizes features.
- `PCA(n_components=2)`: Retains two principal components.
- `fit_transform()`: Learns the principal components and transforms the data.
- `explained_variance_ratio_`: Returns the variance proportion explained by each component.
- `sum()`: Calculates the total variance proportion explained by the selected components.

## 6. PCA Visualization

PCA can be used to project high-dimensional data into two dimensions.

This allows the data to be visualized using a scatter plot.

Example:

```python
import matplotlib.pyplot as plt

plt.scatter(
    X_pca[:, 0],
    X_pca[:, 1]
)

plt.xlabel("Principal Component 1")
plt.ylabel("Principal Component 2")
plt.title("PCA Visualization")
plt.show()
```

## 7. Advantages and Limitations

**Advantages:**

- Reduces the number of features.
- Helps simplify complex datasets.
- Can improve computational efficiency.
- Supports visualization of high-dimensional data.

**Limitations:**

- Principal components may be difficult to interpret.
- Some information may be lost during transformation.
- PCA captures linear combinations of the original features.
- Results can be affected by feature scaling.

## 8. Key Takeaways

- PCA transforms original features into principal components.
- Principal components are orthogonal to one another.
- Components are ordered based on explained variance.
- The number of components determines the dimensionality of the transformed data.
- PCA helps reduce dimensions while retaining important information.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 4: Principal Component Analysis.