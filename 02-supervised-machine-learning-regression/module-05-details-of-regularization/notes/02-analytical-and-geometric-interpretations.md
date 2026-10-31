# Analytical and Geometric Interpretations of Regularization

## 1. Analytical Interpretation

The analytical interpretation explains regularization through the effect of coefficient penalties on model complexity.

When L1 or L2 penalties are applied, coefficient values are encouraged to become smaller.

Smaller coefficients restrict the range of possible model solutions and can reduce model sensitivity to changes in input features.

### Why Smaller Coefficients Matter

Consider a regression model:

\[
\hat{y} = \beta_0 + \beta_1x_1 + \beta_2x_2
\]

If a coefficient is large, a small change in its corresponding feature can produce a relatively large change in the prediction.

If a coefficient is close to zero, the corresponding feature has a smaller contribution to the prediction.

Therefore, reducing coefficient values can make a model less sensitive to input changes and reduce variance.

### Main Points

- L1 and L2 penalties restrict coefficient values.
- Smaller coefficients can produce simpler models.
- Simpler models generally have lower variance.
- Regularization can improve generalization by controlling model complexity.

## 2. Geometric Interpretation

The geometric interpretation explains regularization as a constrained optimization problem.

Instead of only minimizing prediction error, the model must also satisfy a constraint on the size of its coefficients.

The optimal solution is found where the error contours meet the regularization constraint boundary.

## 3. Ridge Regression Geometry

Ridge Regression uses an L2 constraint:

\[
\sum_{j=1}^{p}\beta_j^2 \leq S
\]

Where:

- \(\beta_j\): Model coefficients.
- \(S\): Maximum allowed squared coefficient magnitude.

For two coefficients, this constraint forms a circular boundary.

The Ridge solution is found where the ordinary least squares error contour meets the circular constraint.

Because the boundary is smooth, the solution generally shrinks coefficients toward zero without making them exactly zero.

## 4. LASSO Geometry

LASSO uses an L1 constraint:

\[
\sum_{j=1}^{p}|\beta_j| \leq S
\]

For two coefficients, this constraint forms a diamond-shaped boundary.

The optimal solution is found where the error contour meets the diamond boundary.

The diamond has sharp corners along the coefficient axes. These corners correspond to solutions where one or more coefficients are exactly zero.

This explains why LASSO is more likely to perform feature selection than Ridge Regression.

## 5. Comparing Ridge and LASSO Geometry

| Aspect | Ridge | LASSO |
|---|---|---|
| Penalty | L2 | L1 |
| Constraint shape in two dimensions | Circle | Diamond |
| Coefficient behavior | Shrinks coefficients | Shrinks and may zero coefficients |
| Feature selection | Generally does not eliminate features | Can eliminate features |

## 6. Why LASSO Can Produce Zero Coefficients

The geometric shape of the LASSO constraint has sharp corners where coefficient values can be zero.

When the error contour meets one of these corners, the resulting solution may have a coefficient equal to zero.

A zero coefficient means that the corresponding feature does not contribute to the model prediction.

Ridge uses a circular constraint without the same sharp corners, so its coefficients are generally reduced rather than eliminated.

## Key Takeaway

The analytical interpretation explains why smaller coefficients reduce model sensitivity. The geometric interpretation explains why Ridge generally shrinks coefficients while LASSO can set some coefficients exactly to zero.