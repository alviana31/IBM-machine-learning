# Ridge, LASSO, and Elastic Net

## 1. Ridge Regression (L2 Regularization)

Ridge Regression is a regularization method that adds a penalty based on the squared values of the model coefficients.

Its penalty term is:

\[
R(w) = \sum_{j=1}^{p} w_j^2
\]

The regularized objective can be represented as:

\[
J(w) = M(w) + \lambda \sum_{j=1}^{p}w_j^2
\]

### Characteristics

- Uses L2 regularization.
- Penalizes large coefficient values.
- Shrinks coefficients toward zero.
- Usually does not make coefficients exactly zero.
- Retains features while reducing their influence.
- Can be computationally efficient.

### Implementation with Scikit-learn

```python
from sklearn.linear_model import Ridge

ridge_model = Ridge(alpha=1.0)

ridge_model.fit(X_train_scaled, y_train)

ridge_predictions = ridge_model.predict(X_test_scaled)
```

The `alpha` parameter controls the regularization strength.

## 2. LASSO Regression (L1 Regularization)

LASSO stands for Least Absolute Shrinkage and Selection Operator.

It uses the absolute values of model coefficients as its penalty.

The penalty term is:

\[
R(w) = \sum_{j=1}^{p}|w_j|
\]

The regularized objective can be represented as:

\[
J(w) = M(w) + \lambda \sum_{j=1}^{p}|w_j|
\]

### Characteristics

- Uses L1 regularization.
- Penalizes the absolute values of coefficients.
- Shrinks coefficient values.
- Can make some coefficients exactly zero.
- Performs feature selection.
- Can improve model interpretability by removing less useful features.

### Implementation with Scikit-learn

```python
from sklearn.linear_model import Lasso

lasso_model = Lasso(alpha=0.1)

lasso_model.fit(X_train_scaled, y_train)

lasso_predictions = lasso_model.predict(X_test_scaled)
```

The `alpha` parameter controls the regularization strength.

## 3. Elastic Net

Elastic Net combines L1 and L2 regularization.

It combines the coefficient penalties used by LASSO and Ridge Regression.

A simplified objective function is:

\[
J(w) = M(w) + \lambda \left[
\alpha \sum_{j=1}^{p}|w_j|
+
\frac{1-\alpha}{2}\sum_{j=1}^{p}w_j^2
\right]
\]

Where:

- \(M(w)\): Original cost function.
- \(\lambda\): Overall regularization strength.
- \(\alpha\): Controls the balance between L1 and L2 penalties.

### Characteristics

- Combines L1 and L2 regularization.
- Can shrink coefficient values.
- Can set some coefficients to zero.
- Supports feature selection.
- Requires tuning both regularization strength and the L1/L2 balance.

### Implementation with Scikit-learn

```python
from sklearn.linear_model import ElasticNet

elastic_model = ElasticNet(
    alpha=0.1,
    l1_ratio=0.5
)

elastic_model.fit(X_train_scaled, y_train)

elastic_predictions = elastic_model.predict(X_test_scaled)
```

In Scikit-learn, `l1_ratio` controls the balance between L1 and L2 penalties.

## 4. Comparing Ridge, LASSO, and Elastic Net

| Aspect | Ridge | LASSO | Elastic Net |
|---|---|---|---|
| Regularization | L2 | L1 | L1 + L2 |
| Penalty | Squared coefficients | Absolute coefficients | Combination of both |
| Shrinks coefficients | Yes | Yes | Yes |
| Can set coefficients to zero | Generally no | Yes | Yes |
| Feature selection | Limited | Yes | Yes |
| Main purpose | Reduce coefficient size | Reduce coefficients and select features | Combine both approaches |

## 5. Choosing a Regularization Method

The choice depends on the objective and characteristics of the dataset.

### Choose Ridge When:

- The goal is to reduce large coefficient values.
- Most features may contribute useful information.
- A method that retains all features is preferred.

### Choose LASSO When:

- Feature selection is important.
- Some features may be unnecessary.
- A simpler and more interpretable model is desired.

### Choose Elastic Net When:

- Both L1 and L2 penalties are useful.
- A combination of coefficient shrinkage and feature selection is desired.
- The balance between the two penalties can be tuned.

The best method should be evaluated using validation data or cross-validation rather than selected based on assumptions alone.

## 6. Polynomial Features and Regularization

Polynomial regression can generate many additional features, especially when the polynomial degree increases.

This can make the model more complex and increase the risk of overfitting.

Regularization can be combined with polynomial features to control coefficient values and reduce model complexity.

### Example

```python
from sklearn.preprocessing import PolynomialFeatures, StandardScaler
from sklearn.linear_model import Ridge
from sklearn.pipeline import make_pipeline

model = make_pipeline(
    PolynomialFeatures(degree=3),
    StandardScaler(),
    Ridge(alpha=1.0)
)

model.fit(X_train, y_train)

y_pred = model.predict(X_test)
```

The pipeline performs the following steps:

1. Generates polynomial features.
2. Scales the generated features.
3. Trains a Ridge regression model.
4. Uses the fitted pipeline to generate predictions.

## 7. Important Considerations

- Increasing regularization strength generally increases bias and reduces variance.
- Too much regularization may cause underfitting.
- Too little regularization may leave the model vulnerable to overfitting.
- Feature scaling is important when applying coefficient penalties.
- Cross-validation can help select suitable regularization parameters.
- LASSO's feature selection can improve interpretability, but removing features may be undesirable if many features contain useful information.

## Key Takeaway

Ridge, LASSO, and Elastic Net are regularization methods used to control model complexity. Ridge uses L2 penalties, LASSO uses L1 penalties, and Elastic Net combines both. The appropriate method depends on the dataset and the objective of the analysis.