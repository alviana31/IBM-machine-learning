# Bagging and Random Forest

## 1. Bootstrap Aggregating (Bagging)

Bagging stands for Bootstrap Aggregating.

It is an ensemble method that combines multiple models trained using different bootstrap samples of the original training dataset.

A bootstrap sample is created by randomly selecting observations from the dataset with replacement.

Each model is trained using a different sample, and their predictions are combined to produce the final result.

## 2. How Bagging Works

The general process is:

1. Start with the original training dataset.
2. Create multiple bootstrap samples by sampling with replacement.
3. Train a separate model using each sample.
4. Generate predictions from each trained model.
5. Combine the predictions to obtain the final result.

For classification, the final prediction can be determined through majority voting.

## 3. Why Bagging Helps

Bagging aims to reduce variance by combining predictions from multiple models.

If the models are sufficiently different, combining their predictions can produce more stable results than relying on a single model.

However, when the models are highly correlated, the reduction in variance becomes more limited.

An advantage of Bagging is that the individual models can be trained in parallel because they are built independently.

## 4. Out-of-Bag Error

Because bootstrap sampling uses replacement, some observations may not be selected for a particular model's training sample.

These observations are called out-of-bag (OOB) observations for that model.

Out-of-bag predictions can be used to estimate model performance without requiring a separate validation sample for that purpose.

## 5. Random Forest

Random Forest is an ensemble method based on multiple decision trees.

It follows a similar approach to Bagging but introduces additional randomness by selecting a subset of features when building each tree split.

This helps make the trees less correlated with one another.

According to the course material, the default feature subset size is commonly:

- Classification: square root of the total number of features.
- Regression: one-third of the total number of features.

## 6. Extra Trees

Extra Trees, or Extremely Randomized Trees, introduces additional randomness into the tree-building process.

Instead of relying only on a greedy search to find split variables and split points, it creates splits using random choices.

This makes the method different from standard Random Forest.

## 7. Implementing Bagging

Example using Scikit-learn:

```python
from sklearn.ensemble import BaggingClassifier
from sklearn.tree import DecisionTreeClassifier

bagging_model = BaggingClassifier(
    estimator=DecisionTreeClassifier(),
    n_estimators=50,
    random_state=42,
    n_jobs=-1
)

bagging_model.fit(X_train, y_train)

y_pred = bagging_model.predict(X_test)
```

Explanation:

- `BaggingClassifier`: Creates a Bagging classification model.
- `estimator`: Defines the base model.
- `n_estimators=50`: Uses 50 base estimators.
- `n_jobs=-1`: Allows parallel processing using available CPU cores.
- `fit()`: Trains the ensemble.
- `predict()`: Generates the final predictions.

## 8. Implementing Random Forest

```python
from sklearn.ensemble import RandomForestClassifier

rf_model = RandomForestClassifier(
    n_estimators=100,
    random_state=42,
    n_jobs=-1
)

rf_model.fit(X_train, y_train)

y_pred = rf_model.predict(X_test)
```

## 9. Key Takeaways

- Bagging trains multiple models using bootstrap samples.
- Classification predictions can be combined through majority voting.
- Bagging can reduce variance and can be trained in parallel.
- Out-of-bag observations can help estimate model performance.
- Random Forest adds random feature selection to the Bagging approach.
- Extra Trees introduces additional randomness when creating splits.