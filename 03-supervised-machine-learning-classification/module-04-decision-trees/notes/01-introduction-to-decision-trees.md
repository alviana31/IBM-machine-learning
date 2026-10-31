# Introduction to Decision Trees

## 1. Definition of Decision Trees

A Decision Tree is a supervised machine learning algorithm used for classification and regression.

For classification, the algorithm makes predictions by following a series of decisions based on the features of the input data.

The structure resembles a tree, where each internal node represents a decision, each branch represents an outcome, and each leaf node represents a final prediction.

## 2. Main Components of a Decision Tree

A decision tree consists of several important components:

- **Root Node:** The starting point of the tree, representing the first decision.
- **Decision Node:** A node where a condition or test is applied to a feature.
- **Branch:** A path that represents the result of a decision.
- **Leaf Node:** The final node that provides the predicted class.

## 3. How Decision Trees Work

A decision tree makes predictions by following a sequence of rules.

The general process is:

1. Start at the root node.
2. Evaluate the condition based on a feature.
3. Follow the branch that matches the result.
4. Continue through the decision nodes.
5. Reach a leaf node to obtain the prediction.

## 4. Example of Decision Tree Classification

A decision tree can be used to predict whether a person will play outdoor sports based on weather conditions.

Possible features include:

- Weather
- Temperature
- Humidity
- Wind conditions

The model learns decision rules from the training data and uses them to classify new observations.

## 5. Decision Trees in Classification

In classification tasks, the leaf nodes represent class labels.

For example, a decision tree may classify a transaction as:

- Legitimate
- Fraudulent

The prediction depends on the feature conditions learned during training.

## 6. Advantages of Decision Trees

- Easy to understand and interpret.
- Can represent decision rules visually.
- Can handle classification tasks.
- Does not require feature scaling in the same way as distance-based algorithms such as KNN.

## 7. Disadvantages of Decision Trees

- Can become overly complex.
- May overfit the training data.
- Small changes in training data can produce a different tree.
- The quality of predictions depends on how the tree is constructed.

## 8. Summary

Decision Trees classify observations by following a sequence of feature-based decisions. Their tree structure makes the prediction process relatively easy to understand and interpret.