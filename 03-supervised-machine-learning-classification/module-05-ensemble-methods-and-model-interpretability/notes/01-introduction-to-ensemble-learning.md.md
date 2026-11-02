# Introduction to Ensemble Learning

## 1. Definition

Ensemble Learning is a machine learning approach that combines multiple models to produce a final prediction.

Instead of relying on a single model, ensemble methods use several models to improve prediction performance and generalization.

The models used in an ensemble are often called base learners or estimators.

## 2. Why Use Ensemble Methods?

A single model may have limitations when learning patterns from a dataset.

Combining multiple models can help:

- Improve prediction performance.
- Reduce model variance.
- Produce more stable predictions.
- Capture different patterns in the data.
- Improve generalization to unseen observations.

Tree ensembles are particularly useful when relationships between predictor variables and the target are not easily represented by simple linear or polynomial models.

## 3. Common Ensemble Methods

The course introduces several popular ensemble approaches:

### Bagging

Bagging combines multiple models trained on bootstrap samples of the training dataset.

### Random Forest

Random Forest extends the Bagging approach by introducing randomness in the selection of features used to build each tree.

### Boosting

Boosting trains models sequentially, focusing on observations that previous models handled poorly.

### Stacking

Stacking combines predictions from different models using another model or a voting strategy.

## 4. Independent and Sequential Training

Ensemble methods can differ in how their models are trained.

- Bagging generally trains models independently using different bootstrap samples.
- Boosting trains models sequentially, with later models focusing on previous errors.
- Stacking combines predictions from multiple models to generate a final prediction.

## 5. Key Takeaways

- Ensemble learning combines multiple models.
- Bagging, Random Forest, Boosting, and Stacking are common ensemble approaches.
- Different ensemble methods use different strategies to combine predictions.
- Ensemble methods can improve generalization and prediction performance.