# Distance Measurement in KNN

## 1. Importance of Distance

Distance measurement is an important part of KNN because the algorithm identifies the nearest observations to make predictions.

The basic assumption is that data points that are close to each other are likely to have similar outcomes.

The distance between a new observation and the training observations determines which points become its nearest neighbors.

## 2. Euclidean Distance

Euclidean distance measures the straight-line distance between two points.

For two points with multiple features, the formula is:

\[
d(x,y) = \sqrt{\sum_{i=1}^{n}(x_i-y_i)^2}
\]

Where:

- \(x_i\) represents the feature value of the first point.
- \(y_i\) represents the feature value of the second point.
- \(n\) represents the number of features.

Euclidean distance is commonly used because it is easy to understand and interpret geometrically.

## 3. Manhattan Distance

Manhattan distance calculates the sum of the absolute differences between two points.

The formula is:

\[
d(x,y) = \sum_{i=1}^{n}|x_i-y_i|
\]

It is also known as L1 distance.

Unlike Euclidean distance, Manhattan distance measures movement along individual dimensions rather than a direct straight-line path.

## 4. Comparison

| Distance | Calculation | Description |
|---|---|---|
| Euclidean | Square root of squared differences | Straight-line distance |
| Manhattan | Sum of absolute differences | Distance along each dimension |

Both measurements are commonly used in KNN.

## 5. Python Example

```python
from sklearn.metrics import pairwise_distances

distance_euclidean = pairwise_distances(
    X, metric="euclidean"
)

distance_manhattan = pairwise_distances(
    X, metric="manhattan"
)
```

The `metric` parameter determines the distance measurement used.

## 6. Key Takeaways

- KNN relies on distance to identify neighboring observations.
- Euclidean distance measures straight-line distance.
- Manhattan distance adds the absolute differences across features.
- The scale of variables can affect distance calculations.
- Selecting an appropriate distance measurement is important for KNN performance.