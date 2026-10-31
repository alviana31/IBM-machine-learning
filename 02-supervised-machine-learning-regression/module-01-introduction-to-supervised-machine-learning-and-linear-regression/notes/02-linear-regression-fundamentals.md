# Linear Regression Fundamentals

## 1. What is Linear Regression?

Linear regression is a supervised machine learning algorithm used to model the relationship between input variables and a continuous numerical target.

The algorithm attempts to find a linear relationship that can be used to predict the target value based on the input features.

For a simple linear regression with one feature, the model is represented as:

\[
\hat{y} = \beta_0 + \beta_1 x
\]

Where:

- \(\hat{y}\): Predicted value.
- \(x\): Input feature.
- \(\beta_0\): Intercept.
- \(\beta_1\): Slope or coefficient.

## 2. Understanding the Coefficients

### Intercept (\(\beta_0\))

The intercept represents the predicted value of the target when the input feature is zero.

### Slope (\(\beta_1\))

The slope represents how much the predicted target changes when the input feature increases by one unit.

A positive slope indicates that the predicted target increases as the feature increases. A negative slope indicates the opposite relationship.

## 3. Linear Regression Example

Consider a model that predicts movie revenue based on its production budget.

Suppose the model is:

\[
\hat{y} = 80 + 0.6x
\]

Where:
- Intercept = 80 million.
- Slope = 0.6.
- \(x\) = Movie production budget in millions.
- \(\hat{y}\) = Predicted revenue in millions.

If the production budget is 160 million:

\[
\hat{y} = 80 + (0.6 \times 160)
\]

\[
\hat{y} = 176
\]

The predicted revenue is 176 million.

This example shows how a linear regression model uses an input feature to estimate a numerical outcome.

## 4. Prediction and Interpretation

Linear regression can be used for two different purposes:

### Prediction

The objective is to produce accurate predictions for new observations.

### Interpretation

The objective is to understand the relationship between input features and the target variable.

These objectives can involve different modeling priorities. A model that is useful for prediction does not always provide the simplest or clearest interpretation.

## 5. Residuals and Prediction Errors

A residual is the difference between the actual target value and the predicted value.

\[
e_i = y_i - \hat{y}_i
\]

Where:
- \(e_i\): Residual or prediction error.
- \(y_i\): Actual value.
- \(\hat{y}_i\): Predicted value.

Residuals help describe how far the model's predictions are from the actual observations.

## 6. Linear Regression with Scikit-learn

Scikit-learn provides the `LinearRegression` class for building linear regression models.

### Import the Library

```python
from sklearn.linear_model import LinearRegression
```

### Create the Model

```python
model = LinearRegression()
```

### Train the Model

```python
model.fit(X_train, y_train)
```

The `fit()` method trains the model using the input features and target values.

### Make Predictions

```python
y_pred = model.predict(X_test)
```

The `predict()` method generates predictions using the trained model.

### Access Model Coefficients

```python
print(model.intercept_)
print(model.coef_)
```

- `intercept_` returns the model intercept.
- `coef_` returns the learned feature coefficients.

## Key Takeaway

Linear regression models the relationship between input features and a numerical target. Its coefficients describe the fitted relationship, while the trained model can be used to make predictions on new data.