# Non-Negative Matrix Factorization

## 1. Introduction

Non-Negative Matrix Factorization (NMF) is a matrix decomposition technique that represents an original nonnegative matrix using two smaller nonnegative matrices.

The two resulting matrices are commonly called W and H.

NMF is useful when the original data contains only positive or zero values, such as word counts and image pixel values.

## 2. Basic Concept

Suppose the original matrix is represented by V.

NMF decomposes V into two matrices:

\[
V \approx W \times H
\]

Where:

- **V:** Original nonnegative data matrix.
- **W:** First factor matrix.
- **H:** Second factor matrix.

Both W and H contain nonnegative values.

The multiplication of W and H produces an approximation of the original matrix V.

## 3. Nonnegative Constraint

The main characteristic of NMF is that it does not allow negative values in the input matrix or the factor matrices.

This makes NMF suitable for data such as:

- Word frequency or word count.
- Image pixel intensity.
- Other nonnegative numerical measurements.

The nonnegative constraint can also make the resulting components easier to interpret in some applications.

## 4. Selecting the Number of Components

The number of components is selected by the user.

For example, when analyzing a collection of documents, the user may choose five topics.

The number of topics determines the number of components used to represent the original document data.

Selecting the number of components is an important part of applying NMF.

## 5. Matrix Reconstruction

After factorization, W and H can be multiplied to reconstruct an approximation of the original matrix.

\[
\hat{V} = W \times H
\]

Here, \(\hat{V}\) represents the reconstructed matrix.

The reconstructed matrix approximates the original input matrix rather than necessarily reproducing every value exactly.

## 6. NMF with Python

The following example demonstrates how to apply NMF using Scikit-learn.

```python
from sklearn.decomposition import NMF

# Create an NMF model
nmf = NMF(
    n_components=5,
    random_state=42,
    max_iter=500
)

# Fit the model and transform the input data
W = nmf.fit_transform(X)

# Obtain the component matrix
H = nmf.components_

# Reconstruct an approximation of the original matrix
X_approx = W @ H
```

### Code Explanation

- `NMF`: Imports the Non-Negative Matrix Factorization algorithm.
- `n_components=5`: Sets the number of components to five.
- `random_state=42`: Helps make the initialization reproducible.
- `max_iter=500`: Sets the maximum number of iterations.
- `fit_transform(X)`: Fits the model and returns the W matrix.
- `components_`: Returns the H matrix.
- `W @ H`: Reconstructs an approximation of the original matrix.

**Important:** The input matrix `X` must contain only nonnegative values.

## 7. Key Takeaways

- NMF decomposes a nonnegative matrix into W and H.
- Both factor matrices contain nonnegative values.
- The number of components is selected by the user.
- The multiplication of W and H approximates the original matrix.
- Scikit-learn provides an NMF implementation through `sklearn.decomposition`.

## 8. Conclusion

NMF is useful for decomposing nonnegative data into smaller representations. Its ability to represent data through nonnegative components makes it suitable for applications such as document analysis and image processing.