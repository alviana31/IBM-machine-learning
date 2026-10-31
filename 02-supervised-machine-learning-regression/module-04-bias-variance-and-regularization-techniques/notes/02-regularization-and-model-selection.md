# Regularization and Model Selection

## 1. What is Regularization?

Regularization is a technique used to control model complexity and reduce overfitting.

It works by adding a penalty term to the original cost function. This penalty discourages the model from assigning excessively large values to its coefficients.

In linear regression, the original objective is commonly based on minimizing prediction error, such as Mean Squared Error (MSE).

With regularization, the objective becomes:

\[
J(w) = M(w) + \lambda R(w)
\]

Where:

- \(J(w)\): Regularized cost function.
- \(M(w)\): Original model cost or error.
- \(\lambda\): Regularization strength.
- \(R(w)\): Penalty function based on model coefficients.

## 2. Why is Regularization Important?

A complex model may fit the training data very closely but perform poorly on unseen observations.

Regularization helps control this complexity by shrinking coefficient values.

Its benefits include:

- Reducing overfitting.
- Controlling large model coefficients.
- Reducing model complexity.
- Helping improve generalization.
- Supporting feature selection in certain methods.

## 3. Understanding Regularization Strength

The parameter \(\lambda\) controls how strongly the model is penalized.

### Small Regularization Strength

When \(\lambda\) is small:

- The penalty has less influence.
- Coefficients are less restricted.
- The model can remain more complex.
- The risk of overfitting may remain high.

### Large Regularization Strength

When \(\lambda\) is large:

- The penalty has more influence.
- Coefficients are pushed toward smaller values.
- The model becomes more restricted.
- The risk of underfitting may increase.

The objective is to find a suitable regularization strength that balances model complexity and prediction performance.

## 4. Regularization and Model Selection

Model selection involves comparing different models and choosing one that best fits the objective of the analysis.

For prediction tasks, validation data or cross-validation can be used to compare model performance.

The selection process may include:

1. Choosing candidate models.
2. Selecting regularization methods.
3. Testing different regularization strengths.
4. Evaluating performance using validation data.
5. Selecting the model with suitable generalization performance.

Cross-validation can help identify an appropriate regularization strength.

## 5. Feature Scaling and Regularization

Feature scaling is important when applying regularization.

If input features have very different numerical scales, coefficient penalties may affect them unevenly.

Standardization is one common approach.

### StandardScaler Example

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train_scaled = scaler.fit_transform(X_train)

X_test_scaled = scaler.transform(X_test)
```

The scaler is fitted using training data only. The same transformation is then applied to test data.

This helps prevent information from the test set from influencing the training process.

## 6. Recursive Feature Elimination

Recursive Feature Elimination (RFE) is a feature selection technique introduced in this module.

It works by repeatedly training a model, ranking features based on their importance, and removing less important features until the selected number of features remains.

RFE can help reduce the number of input features and simplify a model.

## Key Takeaway

Regularization adds a penalty to the model's cost function to control coefficient size and reduce overfitting. Model selection and cross-validation can help determine suitable regularization settings.