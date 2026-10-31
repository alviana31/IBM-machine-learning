# Ensemble Methods and Bagging

## 1. Definition of Ensemble Methods

Ensemble methods are machine learning techniques that combine predictions from multiple models to produce a final prediction.

Instead of relying on a single model, ensemble learning uses several models to improve prediction performance.

The models used in an ensemble are often called base learners or estimators.

## 2. Why Use Ensemble Methods?

A single machine learning model may have limitations when learning patterns from data.

Ensemble methods aim to improve the overall prediction by combining multiple models.

Some potential benefits include:

- Improving prediction accuracy.
- Reducing model variance.
- Producing more stable predictions.
- Combining the strengths of different models.

## 3. Bagging

Bagging stands for Bootstrap Aggregating.

It is an ensemble technique that trains multiple models using different bootstrap samples from the original training dataset.

A bootstrap sample is created by randomly selecting observations from the training data with replacement.

The predictions from the individual models are then combined to produce the final result.

## 4. How Bagging Works

The general process of bagging is:

1. Start with the original training dataset.
2. Create multiple bootstrap samples.
3. Train a separate model using each sample.
4. Generate predictions from each trained model.
5. Combine the predictions into a final result.

For classification, the final prediction is commonly determined through majority voting.

## 5. Bootstrap Sampling

Bootstrap sampling creates different training subsets by randomly selecting observations with replacement.

Because sampling is performed with replacement, the same observation may appear more than once in a bootstrap sample, while some observations may not be selected.

This allows individual models to learn from slightly different versions of the training data.

## 6. Advantages of Bagging

- Can reduce variance.
- Can improve model stability.
- Helps reduce overfitting in some high-variance models.
- Allows multiple models to be trained independently.

## 7. Summary

Ensemble methods combine multiple models to produce a final prediction. Bagging is one approach that uses bootstrap samples to train several models and combines their predictions.

The main purpose of bagging is to create a more stable prediction by reducing the effect of variations in individual models.