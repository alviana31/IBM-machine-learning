# Kernel Functions and Parameters

## 1. Kernel Functions

A kernel function measures relationships between data points in a transformed feature space.

In Kernel PCA, kernel functions allow the algorithm to capture nonlinear patterns that may not be represented effectively through linear transformations.

The module introduces several kernel choices:

- Linear
- Polynomial (Poly)
- Radial Basis Function (RBF)
- Sigmoid
- Cosine

## 2. Types of Kernel Functions

### A. Linear Kernel

The linear kernel represents relationships using the inner product of two vectors.

It is suitable when the data structure can be represented using linear relationships.

### B. Polynomial Kernel

The polynomial kernel captures relationships involving polynomial combinations of the original features.

It can represent more complex relationships than a linear kernel.

### C. Radial Basis Function (RBF) Kernel

The RBF kernel is commonly used to capture nonlinear relationships.

It measures similarity based on the distance between data points.

### D. Sigmoid Kernel

The sigmoid kernel uses a hyperbolic tangent function to represent relationships between data points.

### E. Cosine Kernel

The cosine kernel measures similarity based on the angle between vectors.

## 3. Important Kernel PCA Parameters

Kernel PCA introduces additional parameters that influence the transformation.

### A. Gamma

Gamma is an important parameter for kernels such as RBF.

It controls how strongly the similarity between data points is influenced by their distance.

Different gamma values can produce different levels of complexity in the resulting nonlinear transformation.

### B. Alpha

Alpha is a regularization parameter used when fitting the inverse transformation.

It influences the regularization applied during reconstruction.

## 4. Kernel PCA Configuration

Example based on the module material:

```python id="t2f4ph"
from sklearn.decomposition import KernelPCA

kernel_pca = KernelPCA(
    kernel="rbf",
    gamma=10,
    fit_inverse_transform=True,
    alpha=0.1
)
```

The selected kernel and parameter values should be evaluated based on the characteristics of the dataset.

## 5. Hyperparameter Tuning

Different kernel choices and gamma values can produce different results.

Grid search can be used to explore combinations of hyperparameters.

In unsupervised learning, selecting the best model can be more challenging because there are no target labels available for standard supervised evaluation.

One approach discussed in the course is to evaluate reconstruction error using Mean Squared Error (MSE).

The general idea is:

1. Fit Kernel PCA to the data.
2. Transform the original data.
3. Apply the inverse transformation.
4. Compare the reconstructed data with the original data.
5. Calculate the reconstruction error.
6. Compare different parameter combinations.

A lower reconstruction error indicates a closer reconstruction, although it should not be treated as the only measure of usefulness for every unsupervised learning task.

## 6. Key Takeaways

- Kernel PCA supports several kernel functions.
- Common options include linear, polynomial, RBF, sigmoid, and cosine.
- Gamma affects the behavior of the RBF kernel.
- Alpha controls regularization for the inverse transformation.
- Grid search can help explore different parameter combinations.
- Reconstruction error can be used as one evaluation approach.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 5: Kernel PCA and Hyperparameter Tuning.