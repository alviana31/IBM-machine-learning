# Training and Test Splits

## 1. What is a Training and Test Split?

A training and test split is a technique used to divide a dataset into two separate subsets:

- **Training Set:** The data used to train or fit the machine learning model.
- **Test Set:** The data used to evaluate the model's performance on observations that were not used during training.

The purpose of this approach is to understand how well a model can perform on new data.

## 2. Why is Data Splitting Important?

Evaluating a model using only the data it was trained on may give an overly optimistic result.

A model might learn the training data too closely and perform poorly on new observations. This problem is known as overfitting.

By separating training and test data, we can measure whether the model is able to generalize beyond the examples it has already seen.

## 3. Training Error and Test Error

### Training Error

Training error measures the difference between the actual values and the predictions made on the training data.

It shows how well the model fits the data used during training.

### Test Error

Test error measures the prediction error on the test data.

It provides an indication of how well the model performs on unseen observations.

### Important Observation

As model complexity increases, training error tends to decrease. However, a more complex model does not automatically perform better on unseen data.

This is why evaluating a model using separate test data is important.

## 4. Splitting Data with Scikit-learn

Scikit-learn provides the `train_test_split()` function to divide a dataset.

### Import the Function

```python
from sklearn.model_selection import train_test_split
```

### Prepare Features and Target

```python
X = df.drop("target", axis=1)
y = df["target"]
```

Replace `"target"` with the actual target column in the dataset.

### Split the Dataset

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Explanation:

- `X`: Input features.
- `y`: Target variable.
- `test_size=0.2`: Uses 20% of the observations for testing and the remaining 80% for training.
- `random_state=42`: Makes the random split reproducible.

The resulting variables are:

- `X_train`: Training features.
- `X_test`: Testing features.
- `y_train`: Training target values.
- `y_test`: Testing target values.

## 5. Training and Evaluating a Regression Model

After splitting the dataset, a regression model can be trained using the training set.

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)
```

Generate predictions using the test features:

```python
y_pred = model.predict(X_test)
```

Evaluate the predictions:

```python
from sklearn.metrics import mean_squared_error

mse = mean_squared_error(y_test, y_pred)

print("Test MSE:", mse)
```

The test MSE measures the average squared prediction error on the test set.

## 6. Understanding Overfitting

Overfitting occurs when a model learns the training data too closely, including patterns that may not represent the general relationship in the data.

An overfitted model may have:

- Very low training error.
- Higher test error.
- Poor performance on new observations.

A separate test dataset helps identify whether a model is generalizing well.

## Key Takeaway

Training data is used to fit a model, while test data is used to measure its performance on unseen observations. A good model should not only fit the training data but also generalize to new data.