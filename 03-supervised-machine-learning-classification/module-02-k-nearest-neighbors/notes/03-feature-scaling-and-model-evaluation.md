# Feature Scaling and Model Evaluation

## 1. Feature Scaling

Feature scaling is the process of adjusting numerical features to a comparable scale.

In KNN, feature scaling is important because the algorithm uses distance calculations to identify the nearest neighbors.

If one feature has a much larger numerical range than another, it may dominate the distance calculation and influence the prediction.

## 2. Why Feature Scaling Matters

Consider a dataset with two features:

- Age: values range from 18 to 60.
- Annual Income: values range from 20,000 to 100,000.

Because the income values are much larger, they can have a greater influence on distance calculations.

Feature scaling helps prevent this problem by bringing numerical features into a more comparable range.

## 3. Common Feature Scaling Methods

Two commonly used methods are:

### Min-Max Scaling

Min-Max Scaling transforms values into a specified range, commonly between 0 and 1.

The formula is:

\[
X'=\frac{X-X_{\min}}{X_{\max}-X_{\min}}
\]

### Standardization

Standardization transforms data based on its mean and standard deviation.

The formula is:

\[
Z=\frac{X-\mu}{\sigma}
\]

Where:

- \(X\) = original value
- \(\mu\) = mean
- \(\sigma\) = standard deviation

## 4. Implementing KNN with Scikit-learn

Scikit-learn provides the `KNeighborsClassifier` class for building KNN classification models.

Example:

```python
from sklearn.neighbors import KNeighborsClassifier

knn = KNeighborsClassifier(n_neighbors=5)

knn.fit(X_train, y_train)

y_pred = knn.predict(X_test)
```

The parameter `n_neighbors=5` means that the model considers five nearest neighbors when making a prediction.

## 5. Applying Feature Scaling

Feature scaling can be performed using `StandardScaler`.

Example:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

The scaler is fitted using the training data and then applied to the test data. This helps prevent information from the test set from influencing the scaling process.

## 6. Model Evaluation

After making predictions, the model should be evaluated to understand its classification performance.

For classification tasks, common evaluation metrics include:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

These metrics help assess how well the KNN model classifies observations.

## 7. Summary

Feature scaling is an important preprocessing step for KNN because the algorithm relies on distance calculations.

After scaling the features, a KNN classifier can be implemented using Scikit-learn and evaluated using classification metrics.

The choice of K, feature scaling, and the quality of the dataset can influence the model's performance.