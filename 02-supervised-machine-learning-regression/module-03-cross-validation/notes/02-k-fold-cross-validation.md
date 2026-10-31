# K-Fold Cross-Validation

## 1. What is K-Fold Cross-Validation?

K-Fold Cross-Validation is a cross-validation method that divides a dataset into \(K\) approximately equal-sized subsets, called folds.

The model is trained and evaluated \(K\) times. In each iteration:

- One fold is used as the validation set.
- The remaining \(K-1\) folds are used as the training set.

The process continues until every fold has been used once as the validation set.

## 2. How K-Fold Works

For example, if the dataset is divided into 5 folds:

| Iteration | Training Folds | Validation Fold |
|---|---|---|
| 1 | 2, 3, 4, 5 | 1 |
| 2 | 1, 3, 4, 5 | 2 |
| 3 | 1, 2, 4, 5 | 3 |
| 4 | 1, 2, 3, 5 | 4 |
| 5 | 1, 2, 3, 4 | 5 |

Each fold is used once for validation, while the other folds are used for training.

## 3. Calculating the Average Score

After all iterations are completed, the model produces \(K\) evaluation scores.

The average score can be calculated using:

\[
\text{Average Score} = \frac{1}{K}\sum_{i=1}^{K} S_i
\]

Where:

- \(K\): Number of folds.
- \(S_i\): Evaluation score from each iteration.

For example, suppose a model produces the following scores:

- Fold 1: 0.82
- Fold 2: 0.85
- Fold 3: 0.80
- Fold 4: 0.84
- Fold 5: 0.83

The average score is:

\[
\frac{0.82+0.85+0.80+0.84+0.83}{5}=0.828
\]

The average score is 0.828.

## 4. Implementing K-Fold with Scikit-learn

Scikit-learn provides `KFold` and `cross_val_score` for cross-validation.

### Import the Libraries

```python
from sklearn.model_selection import KFold, cross_val_score
from sklearn.linear_model import LinearRegression
```

### Create the K-Fold Object

```python
kf = KFold(
    n_splits=5,
    shuffle=True,
    random_state=42
)
```

Explanation:

- `n_splits=5`: Divides the dataset into five folds.
- `shuffle=True`: Shuffles the observations before splitting.
- `random_state=42`: Makes the split reproducible.

### Create a Regression Model

```python
model = LinearRegression()
```

### Perform Cross-Validation

```python
scores = cross_val_score(
    model,
    X,
    y,
    cv=kf,
    scoring="r2"
)
```

The `cross_val_score()` function trains and evaluates the model across the specified folds.

### Display the Results

```python
print("Scores:", scores)
print("Average Score:", scores.mean())
```

The output contains the score for each fold and the average score.

## 5. Using Mean Squared Error

For regression problems, cross-validation can also evaluate prediction errors using Mean Squared Error.

```python
mse_scores = cross_val_score(
    model,
    X,
    y,
    cv=kf,
    scoring="neg_mean_squared_error"
)
```

Scikit-learn returns negative values for this scoring option because its scoring convention treats higher scores as better.

To obtain positive MSE values:

```python
mse_scores = -mse_scores

print("MSE Scores:", mse_scores)
print("Average MSE:", mse_scores.mean())
```

For MSE, a lower positive value indicates smaller average squared prediction errors.

## 6. Choosing the Number of Folds

The value of \(K\) determines how many training and validation iterations are performed.

For example:

- 5-Fold Cross-Validation: Five iterations.
- 10-Fold Cross-Validation: Ten iterations.

Increasing the number of folds generally increases the computational cost because the model must be trained more times.

The choice of \(K\) depends on the dataset and available computational resources.

## 7. Important Considerations

- Each observation is used for validation once in standard K-Fold Cross-Validation.
- The remaining observations are used for training in each iteration.
- The average score summarizes model performance across the folds.
- Cross-validation can be used to compare different models.
- For a final unbiased evaluation, keep a separate test set that is not used during model selection.

## Key Takeaway

K-Fold Cross-Validation divides a dataset into multiple folds and evaluates the model repeatedly. The scores from all folds provide a broader assessment of model performance than a single train-test split.