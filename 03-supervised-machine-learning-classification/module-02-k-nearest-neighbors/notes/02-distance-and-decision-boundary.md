# Distance Measurement and Decision Boundaries

## 1. Distance Measurement in KNN

Distance measurement is an important part of the KNN algorithm. It is used to determine how close a new data point is to the observations in the training dataset.

The algorithm selects the nearest observations based on their calculated distances.

One commonly used distance measurement is Euclidean distance.

## 2. Euclidean Distance

Euclidean distance measures the straight-line distance between two points.

For two data points with two features:

\[
A=(x_1,y_1)
\]

\[
B=(x_2,y_2)
\]

The Euclidean distance is calculated using:

\[
d(A,B)=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2}
\]

A smaller distance indicates that two observations are closer to each other.

## 3. Decision Boundary

A decision boundary is a line or region that separates different predicted classes in a classification model.

In KNN, the decision boundary is influenced by:

- The distribution of training data.
- The distance between observations.
- The selected number of neighbors (K).

When a new observation is placed in a particular region, KNN predicts its class based on the nearest training observations.

## 4. The Relationship Between K and Decision Boundaries

The value of K can affect the shape of the decision boundary.

- A small K value can produce a more complex decision boundary.
- A larger K value generally produces a smoother decision boundary.

The choice of K affects how sensitive the model is to individual observations.

## 5. Advantages of KNN

Some advantages of KNN include:

- It is relatively easy to understand and implement.
- It does not require a complex training process.
- It can be used for classification tasks.
- It can adapt to different patterns in the training data.

## 6. Disadvantages of KNN

KNN also has several limitations:

- Prediction can become slow when the training dataset is large.
- It can be sensitive to irrelevant features.
- Its performance can be affected by the choice of K.
- Distance calculations can be affected by differences in feature scales.

## 7. Summary

Distance measurement helps KNN identify the nearest observations, while the decision boundary separates the predicted classes.

The choice of K and the distribution of training data influence the classification results.