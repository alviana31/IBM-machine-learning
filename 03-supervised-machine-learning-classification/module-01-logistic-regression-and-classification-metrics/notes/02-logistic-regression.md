# Logistic Regression

## 1. Introduction

Logistic Regression is a supervised machine learning algorithm commonly used for classification problems.

Although its name contains the word regression, it is primarily used to predict the probability that an observation belongs to a particular class.

For binary classification, the model estimates the probability of an observation belonging to class 1.

## 2. Logistic Function

Logistic Regression uses the sigmoid function to transform a numerical output into a probability between 0 and 1.

The sigmoid function is:

\[
\sigma(z)=\frac{1}{1+e^{-z}}
\]

Where:
- \(z\) represents the linear combination of input features and model coefficients.
- \(e\) is the mathematical constant.
- \(\sigma(z)\) is the predicted probability.

## 3. Classification Threshold

The predicted probability is converted into a class label using a threshold.

A common default threshold is 0.5.

- Probability greater than or equal to 0.5: Class 1.
- Probability below 0.5: Class 0.

The threshold can be adjusted depending on the problem and the cost of different prediction errors.

## 4. Multiclass Logistic Regression

Logistic Regression can also be applied to multiclass classification problems.

Instead of predicting only two possible classes, the model can estimate probabilities for multiple categories.

The predicted class is generally the category with the highest estimated probability.

## 5. Implementing Logistic Regression with Scikit-learn

Example implementation:

```python
from sklearn.linear_model import LogisticRegression

# Create the model
model = LogisticRegression()

# Train the model
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Predict probabilities
y_prob = model.predict_proba(X_test)
```

Explanation:

- `LogisticRegression()` creates the classification model.
- `.fit()` trains the model using training data.
- `.predict()` generates predicted class labels.
- `.predict_proba()` returns predicted probabilities for each class.

## 6. Important Considerations

Before training a Logistic Regression model, consider:

- Preparing the dataset properly.
- Handling missing values.
- Encoding categorical features when necessary.
- Scaling numerical features when appropriate.
- Selecting suitable model parameters.
- Evaluating performance using test data.

## Conclusion

Logistic Regression is a useful classification algorithm that estimates class probabilities using the sigmoid function. It can be applied to binary and multiclass classification tasks.