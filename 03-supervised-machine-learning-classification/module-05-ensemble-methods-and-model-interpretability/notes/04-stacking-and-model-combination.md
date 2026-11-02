# Stacking and Model Combination

## 1. Definition of Stacking

Stacking is an ensemble learning method that combines predictions from multiple models to produce a final prediction.

Unlike Bagging and Boosting, Stacking can combine different types of machine learning models.

The predictions from the base models become inputs for another model or a voting mechanism.

## 2. How Stacking Works

The general process is:

1. Select multiple base models.
2. Train each model using the training data.
3. Generate predictions or predicted class probabilities from each model.
4. Combine the outputs from the base models.
5. Use a final estimator or voting strategy to produce the final prediction.

The models used in Stacking can be different algorithms, such as Logistic Regression, Decision Trees, and Support Vector Machines.

## 3. Combining Predictions

The course discusses two common ways to combine predicted probabilities:

### Majority Voting

Each model provides a prediction, and the final class is selected based on the majority vote.

### Weighted Predictions

Each model's predicted probability is assigned a weight.

Models with higher weights have a greater influence on the final prediction.

## 4. Voting Classifier

Scikit-learn provides `VotingClassifier` to combine multiple classification models.

Two common voting strategies are:

- **Hard Voting:** Uses the predicted class labels from each model and selects the class with the majority vote.
- **Soft Voting:** Uses the predicted class probabilities and combines them to determine the final class.

The course demonstrates soft voting.

Example:

```python
from sklearn.ensemble import VotingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.svm import SVC

voting_model = VotingClassifier(
    estimators=[
        ("logistic", LogisticRegression()),
        ("tree", DecisionTreeClassifier(random_state=42)),
        ("svm", SVC(probability=True, random_state=42))
    ],
    voting="soft"
)

voting_model.fit(X_train, y_train)

y_pred = voting_model.predict(X_test)
```

For soft voting, the base estimators must support probability predictions.

## 5. Stacking Classifier

Scikit-learn also provides `StackingClassifier`.

It combines predictions from multiple base estimators and uses a final estimator to make the final prediction.

By default, the final estimator is Logistic Regression.

Example:

```python
from sklearn.ensemble import StackingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.svm import SVC

estimators = [
    ("tree", DecisionTreeClassifier(random_state=42)),
    ("svm", SVC(probability=True, random_state=42))
]

stacking_model = StackingClassifier(
    estimators=estimators,
    final_estimator=LogisticRegression()
)

stacking_model.fit(X_train, y_train)

y_pred = stacking_model.predict(X_test)
```

The final estimator can be changed to another suitable model.

## 6. Comparison of Ensemble Methods

| Method | Main Approach |
|---|---|
| Bagging | Trains models independently using bootstrap samples |
| Random Forest | Combines trees and adds random feature selection |
| Boosting | Trains models sequentially to improve previous predictions |
| Stacking | Combines outputs from different models using a final estimator or voting |

## 7. Key Takeaways

- Stacking combines different types of models.
- Base model predictions are used to generate a final prediction.
- Voting can use class labels or predicted probabilities.
- Soft voting combines predicted probabilities.
- StackingClassifier uses a final estimator, which defaults to Logistic Regression in Scikit-learn.
- Ensemble methods provide different ways to combine model predictions.