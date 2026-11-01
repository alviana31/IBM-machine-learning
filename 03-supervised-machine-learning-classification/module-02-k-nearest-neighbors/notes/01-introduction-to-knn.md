# Introduction to K-Nearest Neighbors (KNN)

## 1. Definition

K-Nearest Neighbors (KNN) is a supervised machine learning algorithm used for classification and regression.

For classification, KNN predicts the class of a new data point by looking at the classes of its nearest data points in the training dataset.

The algorithm assumes that data points located close to each other are likely to have similar outcomes.

## 2. How KNN Works

The basic steps of KNN classification are:

1. Choose the value of K, which represents the number of neighbors to consider.
2. Calculate the distance between the new data point and the training data points.
3. Identify the K nearest neighbors.
4. Count the class labels of those neighbors.
5. Assign the class with the majority vote to the new data point.

## 3. Understanding the K Parameter

K determines how many neighbors are considered when making a prediction.

For example:

- K = 1: The prediction is based on the closest data point.
- K = 3: The prediction is based on the three closest data points.
- K = 5: The prediction is based on the five closest data points.

A small K value can make the model more sensitive to individual observations and noise.

A larger K value considers more neighbors, which can produce smoother classification decisions but may overlook local patterns.

## 4. Example

Suppose a new observation needs to be classified into Class A or Class B.

If K = 5 and the five nearest neighbors consist of:

- 3 observations from Class A.
- 2 observations from Class B.

The new observation will be classified as Class A because it has the majority vote.

## 5. KNN with Scikit-learn

Example implementation:

```python
from sklearn.neighbors import KNeighborsClassifier

knn = KNeighborsClassifier(n_neighbors=5)

knn.fit(X_train, y_train)

y_pred = knn.predict(X_test)
```

Explanation:

- `KNeighborsClassifier`: Imports the KNN classification algorithm.
- `n_neighbors=5`: Uses five nearest neighbors.
- `fit()`: Trains the model using the training data.
- `predict()`: Predicts the classes of new observations.

## 6. Key Takeaways

- KNN is a supervised learning algorithm.
- Classification is based on the nearest training observations.
- K determines the number of neighbors used for prediction.
- The predicted class is commonly determined through majority voting.
- Distance measurement plays an important role in KNN.