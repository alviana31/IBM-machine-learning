# Distance Metrics

## 1. Definition

Distance metrics are mathematical methods used to measure the distance or difference between data points.

In clustering, distance metrics help determine how close or far apart two observations are. This information is used to identify groups of similar data points.

Different distance metrics can produce different results depending on the characteristics of the dataset.

## 2. Euclidean Distance

Euclidean Distance measures the straight-line distance between two points.

It is commonly used when working with numerical data.

For two points in a two-dimensional space:

\[
d(x,y)=\sqrt{(x_1-y_1)^2+(x_2-y_2)^2}
\]

For multiple dimensions:

\[
d(x,y)=\sqrt{\sum_{i=1}^{n}(x_i-y_i)^2}
\]

Example:

```python
import numpy as np

point_a = np.array([2, 3])
point_b = np.array([5, 7])

distance = np.linalg.norm(point_a - point_b)

print(distance)
```

Euclidean Distance is also known as L2 distance.

## 3. Manhattan Distance

Manhattan Distance measures the distance between two points by adding the absolute differences of their coordinates.

It is similar to moving along horizontal and vertical streets in a city.

The formula is:

\[
d(x,y)=\sum_{i=1}^{n}|x_i-y_i|
\]

Example:

```python
import numpy as np

point_a = np.array([2, 3])
point_b = np.array([5, 7])

distance = np.sum(np.abs(point_a - point_b))

print(distance)
```

Manhattan Distance is also known as L1 distance.

## 4. Cosine Distance

Cosine similarity measures the angle between two vectors rather than focusing directly on their magnitudes.

It is useful when the direction of vectors is more important than their absolute values.

The cosine similarity formula is:

\[
\text{Cosine Similarity}(A,B)=
\frac{A \cdot B}{\|A\|\|B\|}
\]

Cosine distance is commonly defined as:

\[
\text{Cosine Distance}=1-\text{Cosine Similarity}
\]

Example:

```python
from sklearn.metrics.pairwise import cosine_similarity

similarity = cosine_similarity(
    [[1, 2, 3]],
    [[2, 4, 6]]
)

print(similarity)
```

Cosine similarity is often useful for text and document analysis, where the direction of feature vectors can matter more than their magnitude.

## 5. Jaccard Distance

Jaccard similarity measures the similarity between two sets by comparing their intersection and union.

The formula is:

\[
J(A,B)=\frac{|A \cap B|}{|A \cup B|}
\]

Jaccard distance is:

\[
d_J(A,B)=1-J(A,B)
\]

Example:

```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

intersection = len(set_a.intersection(set_b))
union = len(set_a.union(set_b))

jaccard_similarity = intersection / union
jaccard_distance = 1 - jaccard_similarity

print(jaccard_distance)
```

Jaccard distance is useful when comparing sets or binary features.

## 6. Comparison of Distance Metrics

| Metric | Measurement | Common Use |
|---|---|---|
| Euclidean | Straight-line distance | Numerical data |
| Manhattan | Sum of absolute differences | Numerical data |
| Cosine | Difference in vector direction | Text and document vectors |
| Jaccard | Difference between sets | Binary and set-based data |

## 7. Choosing a Distance Metric

The choice of distance metric depends on the data representation and analysis objective.

- Euclidean Distance is suitable when straight-line distance is meaningful.
- Manhattan Distance measures coordinate differences along each dimension.
- Cosine Distance focuses on vector orientation.
- Jaccard Distance compares the overlap between sets.

There is no single distance metric that is best for every dataset.

## 8. Key Takeaways

- Distance metrics measure differences between data points.
- Euclidean and Manhattan distances are commonly used for numerical features.
- Cosine distance focuses on the angle between vectors.
- Jaccard distance measures differences between sets.
- The choice of metric can influence clustering results.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 2: Distance Metrics.