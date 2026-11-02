# Approaches to Unbalanced Classification

## 1. Introduction

There are several techniques for handling unbalanced classification datasets. The course covers class weighting, stratified sampling, random oversampling, synthetic oversampling, nearest-neighbor-based methods, and balanced bagging.

The choice of technique depends on the characteristics of the dataset and the classification problem.

## 2. Class Weighting

Class weighting assigns different importance to different classes during model training.

The minority class can receive a higher weight so that errors involving its observations have a greater influence on the learning process.

This approach can be useful because it does not require directly duplicating or removing observations.

## 3. Stratified Sampling

Stratified sampling divides data while maintaining approximately the same class proportions in each subset.

For example, if a dataset contains 90% majority-class observations and 10% minority-class observations, a stratified split attempts to preserve this proportion in both training and testing sets.

The course recommends using a stratified train-test split before applying resampling techniques.

## 4. Random Oversampling

Random oversampling increases the number of minority-class observations by randomly selecting existing observations and duplicating them.

This method is relatively simple and helps the model see the minority class more frequently during training.

However, repeated observations can increase the risk of overfitting.

## 5. Synthetic Oversampling

Synthetic oversampling creates new minority-class observations instead of only duplicating existing ones.

The course introduces two methods:

### 5.1 SMOTE

Synthetic Minority Oversampling Technique (SMOTE) generates synthetic observations based on the nearest neighbors of minority-class observations.

Rather than simply copying existing records, it creates new examples between nearby minority-class observations.

### 5.2 ADASYN

Adaptive Synthetic Sampling (ADASYN) is another synthetic oversampling technique.

It generates synthetic observations based on the learning difficulty of minority-class examples, giving more attention to examples that are harder to learn.

Both SMOTE and ADASYN use nearest-neighbor-based ideas.

## 6. Nearest-Neighbor-Based Undersampling Methods

The course discusses several methods for reducing majority-class observations or cleaning class boundaries.

### 6.1 NearMiss

NearMiss selects majority-class observations based on their distances to minority-class observations.

The course describes selecting majority-class points whose average distance to a specified number of nearest minority-class points is small.

The intention is to retain majority-class observations near the decision boundary.

**Limitation:** NearMiss can be affected by outliers and noise, which may influence which observations are retained.

### 6.2 Tomek Links

Tomek Links is introduced as a method that can be used to remove observations near overlapping class boundaries.

It can help reduce overlap between classes when used as an undersampling or data-cleaning technique.

### 6.3 Edited Nearest Neighbors

Edited Nearest Neighbors (ENN) uses nearest-neighbor relationships to identify observations that may be inconsistent with their surrounding neighbors.

It can be used to remove noisy observations, including observations near class boundaries.

## 7. Balanced Bagging (Blagging)

The course refers to this technique as "blagging" or balanced bagging.

The main idea is to combine bootstrap sampling with downsampling.

General process:

1. Create bootstrap samples.
2. Downsample the majority class in each bootstrap sample.
3. Use the balanced samples to train individual decision trees.
4. Combine the predictions from the trained trees.

This approach gives the minority class more influence during model training.

## 8. Comparing Balancing Approaches

| Technique | Main Idea | Main Consideration |
|---|---|---|
| Class weighting | Assign different weights to classes | Depends on model support and weight selection |
| Stratified sampling | Preserve class proportions during splitting | Does not itself rebalance the training data |
| Random oversampling | Duplicate minority-class observations | May increase overfitting |
| SMOTE | Generate synthetic minority observations | Depends on nearest-neighbor relationships |
| ADASYN | Generate synthetic observations with more focus on difficult examples | May be affected by noise |
| NearMiss | Select majority observations near minority observations | Can be sensitive to outliers |
| Tomek Links | Identify observations near overlapping class boundaries | Can remove useful boundary observations |
| Edited Nearest Neighbors | Remove observations inconsistent with nearby neighbors | Depends on nearest-neighbor structure |
| Balanced bagging | Downsample majority observations in bootstrap samples | Requires training and combining multiple models |

## 9. Choosing a Technique

It can be difficult to determine the best oversampling or undersampling method by visual inspection alone.

The course emphasizes using cross-validation to compare different approaches.

The material also highlights a general trade-off:

- Undersampling may lead to higher recall for the minority class, but at the cost of precision.
- Oversampling retains the majority-class observations and may provide better precision, but can have lower minority-class recall than undersampling.

These are general tendencies described in the course, not guaranteed outcomes for every dataset.

## 10. Recommended Workflow

A practical workflow for handling unbalanced classification data is:

1. Inspect the class distribution.
2. Perform a stratified train-test split.
3. Apply resampling only to the training data.
4. Train the classification model.
5. Evaluate using suitable classification metrics.
6. Compare different approaches using cross-validation.
7. Select the approach that best supports the project objective.

## 11. Key Takeaways

- Class weighting can increase the importance of minority-class observations.
- Stratified sampling helps preserve class proportions across data splits.
- Random oversampling duplicates existing minority-class observations.
- SMOTE and ADASYN generate synthetic minority-class observations.
- NearMiss, Tomek Links, and Edited Nearest Neighbors use nearest-neighbor relationships.
- Balanced bagging combines bootstrap sampling and downsampling.
- Cross-validation helps compare balancing techniques.

## 12. Conclusion

There is no single balancing technique that is best for every classification problem. The appropriate approach should be selected by evaluating its effect on model performance and the objectives of the classification task.