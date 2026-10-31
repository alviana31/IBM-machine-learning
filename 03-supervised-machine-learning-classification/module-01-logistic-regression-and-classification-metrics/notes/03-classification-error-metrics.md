# Classification Error Metrics

## 1. Introduction

Classification metrics are used to evaluate how well a classification model predicts class labels.

Different metrics provide different perspectives on model performance. Therefore, model evaluation should not rely only on accuracy.

## 2. Confusion Matrix

A confusion matrix compares actual class labels with predicted class labels.

For binary classification, it contains four outcomes:

| Component | Meaning |
|---|---|
| True Positive (TP) | Actual positive, predicted positive |
| True Negative (TN) | Actual negative, predicted negative |
| False Positive (FP) | Actual negative, predicted positive |
| False Negative (FN) | Actual positive, predicted negative |

## 3. Accuracy

Accuracy measures the proportion of correct predictions among all predictions.

\[
Accuracy=\frac{TP+TN}{TP+TN+FP+FN}
\]

Accuracy is useful when classes are reasonably balanced and the costs of different errors are similar.

## 4. Precision

Precision measures how many observations predicted as positive are actually positive.

\[
Precision=\frac{TP}{TP+FP}
\]

A high precision means the model produces relatively few false positive predictions.

## 5. Recall (Sensitivity)

Recall measures how many actual positive observations are correctly identified.

\[
Recall=\frac{TP}{TP+FN}
\]

A high recall means the model identifies a large proportion of actual positive cases.

## 6. Specificity

Specificity measures how many actual negative observations are correctly identified.

\[
Specificity=\frac{TN}{TN+FP}
\]

It is useful when correctly identifying negative cases is important.

## 7. ROC Curve

The Receiver Operating Characteristic (ROC) curve evaluates classification performance across different classification thresholds.

It plots:

- True Positive Rate (TPR), also known as Recall.
- False Positive Rate (FPR).

The False Positive Rate is calculated as:

\[
FPR=\frac{FP}{FP+TN}
\]

The ROC curve helps evaluate how well a model distinguishes between classes.

## 8. Precision-Recall Curve

A Precision-Recall curve shows the relationship between precision and recall at different classification thresholds.

It is particularly useful when working with imbalanced datasets or when the positive class is especially important.

## 9. Implementing Evaluation Metrics with Scikit-learn

```python
from sklearn.metrics import (
    confusion_matrix,
    accuracy_score,
    precision_score,
    recall_score,
    classification_report,
    roc_curve,
    precision_recall_curve
)

# Confusion matrix
cm = confusion_matrix(y_test, y_pred)

# Accuracy
accuracy = accuracy_score(y_test, y_pred)

# Precision
precision = precision_score(y_test, y_pred)

# Recall
recall = recall_score(y_test, y_pred)

# Classification report
print(classification_report(y_test, y_pred))
```

For ROC and Precision-Recall curves, use predicted probabilities rather than predicted class labels:

```python
# Predicted probability for the positive class
y_prob = model.predict_proba(X_test)[:, 1]

# ROC curve
fpr, tpr, thresholds = roc_curve(y_test, y_prob)

# Precision-Recall curve
precision_values, recall_values, pr_thresholds = precision_recall_curve(
    y_test, y_prob
)
```

## 10. Choosing the Right Metric

The appropriate metric depends on the classification problem.

- Accuracy: Overall correctness of predictions.
- Precision: Important when false positives should be minimized.
- Recall: Important when false negatives should be minimized.
- Specificity: Important when identifying negative cases correctly matters.
- ROC Curve: Evaluates the trade-off between true positive and false positive rates.
- Precision-Recall Curve: Helps assess performance when the positive class is important, especially with imbalanced data.

## Conclusion

Classification metrics help evaluate model performance from different perspectives. Understanding these metrics makes it easier to select a model that fits the requirements of a particular classification problem.