# Polynomial Regression

## 1. What is Polynomial Regression?

Polynomial regression is an extension of linear regression that uses polynomial terms to capture nonlinear effects in the relationship between input features and a target variable.

In ordinary simple linear regression, the model has the form:

\[
\hat{y} = \beta_0 + \beta_1x
\]

Polynomial regression adds higher-degree terms, such as:

\[
\hat{y} = \beta_0 + \beta_1x + \beta_2x^2
\]

A higher-degree polynomial can include additional terms:

\[
\hat{y} = \beta_0 + \beta_1x + \beta_2x^2 + \beta_3x^3
\]

These additional terms allow the model to represent curved patterns in the data.

## 2. Why Use Polynomial Regression?

Not every relationship between a feature and a target variable follows a straight line.

For example, a dataset may show a curved relationship between the number of hours spent studying and an exam score.

A simple linear model may not capture this pattern effectively.

Polynomial regression introduces additional feature terms to help the model represent these nonlinear relationships.

## 3. Understanding Polynomial Features

Polynomial features are additional variables created by raising existing features to different powers.

For a single feature \(x\), a degree-2 polynomial creates:

- \(x\)
- \(x^2\)

A degree-3 polynomial creates:

- \(x\)
- \(x^2\)
- \(x^3\)

The selected degree determines how many polynomial terms are generated.

A higher degree allows more complex curves, but it can also increase the risk of overfitting.

## 4. Polynomial Regression with Scikit-learn

Scikit-learn provides `PolynomialFeatures` to generate polynomial terms.

### Import the Libraries

```python
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression
```

### Create Polynomial Features

```python
poly = PolynomialFeatures(degree=2)

X_poly = poly.fit_transform(X_train)
```

The `degree=2` setting generates polynomial features up to the second degree.

By default, `PolynomialFeatures` also includes a bias column.

### Train the Model

```python
model = LinearRegression()

model.fit(X_poly, y_train)
```

### Transform Test Data and Make Predictions

```python
X_test_poly = poly.transform(X_test)

y_pred = model.predict(X_test_poly)
```

The test data must be transformed using the same fitted polynomial transformer used for the training data.

## 5. Comparing Linear and Polynomial Regression

| Aspect | Linear Regression | Polynomial Regression |
|---|---|---|
| Features | Original features | Original and polynomial features |
| Relationship | Linear in the features | Can represent curved patterns |
| Complexity | Usually simpler | Depends on polynomial degree |
| Risk | May underfit nonlinear patterns | May overfit if degree is too high |

Polynomial regression is still linear in its coefficients. It becomes more flexible by transforming the input features.

## 6. Model Complexity

Increasing the polynomial degree gives the model more flexibility to fit the training data.

However, greater complexity does not always mean better performance.

A model with a very high polynomial degree may fit the training observations closely but perform poorly on unseen data.

For this reason, model performance should be evaluated using data that was not used for training.

## Key Takeaway

Polynomial regression extends linear regression by adding polynomial features. It can capture nonlinear patterns, but the polynomial degree should be selected carefully to avoid unnecessary model complexity and overfitting.