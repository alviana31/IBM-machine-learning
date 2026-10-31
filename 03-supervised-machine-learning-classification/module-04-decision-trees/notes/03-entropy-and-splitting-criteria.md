# Entropy and Splitting Criteria

## 1. Splitting Criteria

A splitting criterion is a measure used by a decision tree algorithm to determine how data should be divided at each decision node.

The goal is to create groups that are more organized in terms of their class labels.

Different criteria can be used to evaluate the quality of a split.

## 2. Entropy

Entropy is a measure of uncertainty or impurity in a dataset.

In decision tree classification, entropy is used to measure how mixed the class labels are within a group.

The entropy formula is:

\[
H(S)=-\sum_{i=1}^{n}p_i\log_2(p_i)
\]

Where:

- \(S\) represents the dataset.
- \(p_i\) represents the proportion of observations belonging to class \(i\).
- \(n\) represents the number of classes.

## 3. Understanding Entropy Values

Entropy helps describe the distribution of class labels.

- **Entropy = 0:** The group contains observations from only one class.
- **Higher entropy:** The group contains a more mixed distribution of classes.

A decision tree generally prefers splits that reduce uncertainty in the resulting groups.

## 4. Information Gain

Information Gain measures the reduction in entropy after a dataset is split.

The formula is:

\[
IG=H(S)-\sum_{j=1}^{k}\frac{|S_j|}{|S|}H(S_j)
\]

Where:

- \(H(S)\) is the entropy before splitting.
- \(S_j\) is a group produced by the split.
- \(|S_j|/|S|\) is the proportion of observations in that group.
- \(H(S_j)\) is the entropy of the resulting group.

A split with higher Information Gain provides a greater reduction in uncertainty.

## 5. Other Splitting Criteria

Besides entropy-based splitting, decision trees can use other criteria.

One common example is Gini impurity.

### Gini Impurity

Gini impurity measures the probability of incorrectly classifying a randomly selected observation if its class label is assigned according to the class distribution in the group.

Its formula is:

\[
Gini(S)=1-\sum_{i=1}^{n}p_i^2
\]

A lower Gini impurity indicates that the group contains a more concentrated distribution of class labels.

## 6. Entropy and Gini Impurity

Both entropy and Gini impurity can be used to evaluate splits in classification trees.

Their main purpose is to measure the impurity of groups created by a split.

The best criterion may depend on the dataset and the implementation being used.

## 7. Implementing Splitting Criteria

In Scikit-learn, the `criterion` parameter can be used to select a splitting criterion.

Example using Gini impurity:

```python
from sklearn.tree import DecisionTreeClassifier

model_gini = DecisionTreeClassifier(
    criterion='gini',
    random_state=42
)
```

Example using entropy:

```python
model_entropy = DecisionTreeClassifier(
    criterion='entropy',
    random_state=42
)
```

The resulting models can be trained and evaluated to compare their classification performance.

## 8. Summary

Entropy measures uncertainty in class labels, while Information Gain measures how much uncertainty is reduced after splitting.

Gini impurity is another criterion used by decision trees to evaluate the quality of splits. These criteria help determine how a decision tree is constructed.