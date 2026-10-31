# Cost Function and Model Evaluation

## 1. What is a Cost Function?

A cost function measures how well a machine learning model's predictions match the actual target values.

It calculates the errors produced by the model and provides a way to evaluate how well the model fits the training data.

A model with a lower cost generally produces smaller errors according to the selected cost function.

## 2. Error Measurement

Prediction error is calculated by comparing the actual value with the predicted value.

\[
e_i = y_i - \hat{y}_i
\]

Different mathematical approaches can be used to measure these errors.

### L1 Norm

The L1 norm uses the absolute values of errors.

\[
L1 = \sum_{i=1}^{n}|y_i-\hat{y}_i|
\]

It measures the total absolute difference between actual and predicted values.

### L2 Norm

The L2 norm uses squared errors.

\[
L2 = \sum_{i=1}^{n}(y_i-\hat{y}_i)^2
\]

Squaring the errors gives larger errors a greater contribution to the total value.

## 3. Mean Squared Error (MSE)

Mean Squared Error is a common cost function used in regression problems.

It calculates the average of squared differences between actual and predicted values.

\[
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
\]

Where:
- \(n\): Number of observations.
- \(y_i\): Actual value.
- \(\hat{y}_i\): Predicted value.

A smaller MSE indicates that the predictions are closer to the actual values according to squared error.

## 4. R-squared

R-squared (\(R^2\)) is a metric used to evaluate how much of the variation in the target variable is explained by the regression model.

Its value is commonly interpreted as follows:

- A value close to 1 indicates that the model explains a large proportion of the variation in the target.
- A value close to 0 indicates that the model explains little of the variation compared with a baseline that predicts the target mean.

The general formula is:

\[
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
\]

Where:
- \(SS_{res}\): Sum of squared residuals.
- \(SS_{tot}\): Total sum of squares.

R-squared helps describe model fit, but it should not be treated as the only measure of model quality.

## 5. Model Evaluation with Scikit-learn

Scikit-learn provides metrics that can be used to evaluate regression models.

### Import the Metrics

```python
from sklearn.metrics import mean_squared_error, r2_score
```

### Calculate Mean Squared Error

```python
mse = mean_squared_error(y_test, y_pred)
print("Mean Squared Error:", mse)
```

### Calculate R-squared

```python
r2 = r2_score(y_test, y_pred)
print("R-squared:", r2)
```

These metrics compare the model predictions with the actual target values.

## 6. Model Evaluation Best Practices

A basic approach to evaluating a regression model includes:

1. Define the objective of the analysis.
2. Select an appropriate cost function or evaluation metric.
3. Train the model using the available training data.
4. Generate predictions.
5. Evaluate the predictions using suitable metrics.
6. Compare different models based on the evaluation results.

The selected metric should match the objective of the analysis.

## 7. Important Considerations

- A low MSE indicates smaller average squared prediction errors.
- A higher R-squared generally indicates that more variation in the target is explained by the model.
- Evaluation metrics should be interpreted in the context of the dataset and the analysis objective.
- A good model should be assessed beyond a single metric.

## Key Takeaway

Cost functions measure prediction errors, while evaluation metrics help assess model performance. MSE measures average squared errors, and R-squared describes the proportion of target variation explained by the regression model.