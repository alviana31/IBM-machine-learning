# Bias-Variance Trade-off

## 1. Understanding Model Error

A machine learning model attempts to learn patterns from data and make predictions.

However, predictions are not always accurate. Model error can come from three main sources:

- Bias
- Variance
- Irreducible Error

Understanding these sources helps explain why a model may perform poorly on training or testing data.

## 2. Bias

Bias refers to the error caused by assumptions that are too simple to represent the actual relationship in the data.

A model with high bias is likely to underfit.

### Characteristics of High Bias

- The model is too simple.
- It cannot capture important patterns in the data.
- Training error is high.
- Test error is also likely to be high.

### Ways to Reduce Bias

- Increase model complexity.
- Add higher-order polynomial features.
- Include relevant input features.
- Obtain more useful data.

## 3. Variance

Variance describes how sensitive a model is to changes in the training data.

A model with high variance may learn the training data too closely, including random noise.

This problem is commonly associated with overfitting.

### Characteristics of High Variance

- The model is too complex.
- Training error is low.
- Test error is significantly higher.
- Small changes in training data may produce different models.

### Ways to Reduce Variance

- Reduce model complexity.
- Use a lower polynomial degree.
- Obtain more training data.
- Apply regularization.

## 4. Irreducible Error

Irreducible error is the part of prediction error that cannot be eliminated by changing the model.

It can result from random noise, measurement errors, or factors that are not available in the dataset.

Even a well-designed model cannot completely eliminate this type of error.

## 5. Understanding the Bias-Variance Trade-off

Bias and variance often move in opposite directions as model complexity changes.

- A model that is too simple may have high bias and low variance.
- A model that is too complex may have low bias and high variance.
- A suitable model attempts to balance bias and variance.

The objective is not simply to minimize training error. The model should also perform well on unseen data.

## 6. Underfitting vs. Overfitting

| Aspect | Underfitting | Overfitting |
|---|---|---|
| Model complexity | Too simple | Too complex |
| Bias | High | Usually low |
| Variance | Usually low | High |
| Training error | High | Low |
| Test error | High | Often much higher than training error |

## 7. Practical Example

Consider a dataset containing house prices and house sizes.

A very simple model may not capture the actual relationship between size and price. This can result in underfitting.

On the other hand, a highly complex model may follow individual training observations too closely and fail to predict prices accurately for new houses. This can result in overfitting.

The goal is to find a model that captures the important relationship without learning unnecessary noise.

## Key Takeaway

The bias-variance trade-off explains the relationship between model complexity and prediction error. A good model should balance bias and variance so that it can perform well on both training and unseen data.