# Regularization Fundamentals

## 1. Reviewing Regularization

Regularization is a technique used to reduce model complexity by adding a penalty to the original cost function.

The purpose is to prevent a model from becoming too complex and overfitting the training data.

Regularization penalizes large coefficient values, encouraging the model to use smaller coefficients.

## 2. Regularization and the Cost Function

In ordinary linear regression, the model attempts to minimize a cost function based on prediction error.

Regularization adds an additional penalty:

\[
J(w) = M(w) + \lambda R(w)
\]

Where:

- \(J(w)\): Regularized objective function.
- \(M(w)\): Original cost function.
- \(\lambda\): Regularization strength.
- \(R(w)\): Penalty function based on model coefficients.

The penalty term controls how strongly large coefficients are discouraged.

## 3. Relationship Between Coefficients and Model Complexity

A coefficient represents how strongly an input feature affects the model prediction.

A large coefficient means that a small change in its corresponding feature can have a relatively large impact on the predicted target.

A smaller coefficient means that the feature has a smaller influence on the prediction.

By restricting coefficient values, regularization reduces the range of possible model solutions.

This can make the model less sensitive to changes in input data and reduce variance.

## 4. Understanding Regularization Strength

The parameter \(\lambda\) controls the strength of the penalty.

### Low Lambda

- Applies a smaller penalty.
- Allows coefficients to take larger values.
- Allows a more flexible model.
- May result in higher variance.

### High Lambda

- Applies a stronger penalty.
- Encourages smaller coefficients.
- Produces a more restricted model.
- Increases bias while reducing variance.

The goal is to find a suitable value that balances model complexity and prediction error.

## 5. Regularization and Feature Selection

Regularization can also reduce the contribution of less useful features.

Ridge Regression generally shrinks coefficients toward zero without setting them exactly to zero.

LASSO can set some coefficients exactly to zero, effectively removing the corresponding features from the model.

This makes LASSO useful when feature selection and interpretability are important.

## 6. Selecting Regularization Strength

Cross-validation can be used to compare different regularization strengths.

The process involves:

1. Choosing a set of candidate regularization values.
2. Training models using different values.
3. Evaluating each model using cross-validation.
4. Comparing the resulting validation scores.
5. Selecting a value that provides suitable generalization performance.

## Key Takeaway

Regularization controls model complexity by penalizing large coefficients. The regularization strength determines how strongly coefficients are restricted, creating a trade-off between bias and variance.