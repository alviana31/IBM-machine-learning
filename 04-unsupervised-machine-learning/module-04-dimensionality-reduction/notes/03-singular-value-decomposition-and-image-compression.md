# Singular Value Decomposition and Image Compression

## 1. Singular Value Decomposition (SVD)

Singular Value Decomposition (SVD) is a matrix factorization technique that decomposes a matrix into three matrices.

For a matrix \(A\), the decomposition can be written as:

\[
A = U\Sigma V^T
\]

Where:

- **U:** Contains the left singular vectors.
- **Σ (Sigma):** Contains the singular values along its diagonal.
- **Vᵀ:** Contains the transposed right singular vectors.

SVD is used in various applications, including data analysis, dimensionality reduction, and image processing.

## 2. Singular Values

Singular values represent the importance of the corresponding components in the matrix decomposition.

Larger singular values generally represent components that contribute more to the structure of the original matrix.

By retaining only selected larger singular values, a lower-rank approximation of the original matrix can be created.

## 3. SVD and Dimensionality Reduction

SVD can be used to create a lower-dimensional representation of a dataset.

The process involves:

1. Decomposing the original matrix.
2. Selecting the most important singular values.
3. Retaining their corresponding singular vectors.
4. Reconstructing an approximation using fewer components.

This allows the data to be represented using fewer values.

## 4. Image Compression Example

An image can be represented as a matrix of pixel values.

For a grayscale image, each matrix element represents the intensity of a pixel.

SVD can decompose this image matrix into smaller components.

By keeping only the most important singular values and their corresponding vectors, the image can be reconstructed with fewer values.

The reconstructed image may lose some details, but it can still preserve much of the original visual information.

This demonstrates how dimensionality reduction can reduce the amount of information needed to represent an image.

## 5. Implementing SVD with Python

NumPy provides the `linalg.svd()` function.

Example:

```python
import numpy as np

# Example matrix
A = np.array([
    [4, 2, 1],
    [3, 5, 2],
    [1, 2, 4]
])

# Apply SVD
U, S, VT = np.linalg.svd(A)

print("U:")
print(U)

print("Singular values:")
print(S)

print("VT:")
print(VT)
```

## 6. Reconstructing a Matrix with Selected Components

A lower-rank approximation can be created by retaining only the first few singular values and corresponding vectors.

Example:

```python
# Keep the first two components
k = 2

U_k = U[:, :k]
S_k = np.diag(S[:k])
VT_k = VT[:k, :]

# Reconstruct the matrix
A_approx = U_k @ S_k @ VT_k

print(A_approx)
```

The reconstructed matrix is an approximation of the original matrix.

## 7. PCA and SVD

PCA and SVD are closely related mathematical techniques.

PCA can be computed using SVD on appropriately centered data.

| Aspect | PCA | SVD |
|---|---|---|
| Main purpose | Dimensionality reduction | Matrix factorization |
| Input | Usually centered data | A general matrix |
| Output | Principal components and scores | U, singular values, and Vᵀ |
| Application | Feature transformation | Matrix decomposition and compression |

## 8. Key Takeaways

- SVD decomposes a matrix into three matrices.
- Singular values indicate the importance of components.
- Keeping selected components creates a lower-rank approximation.
- SVD can be applied to image compression.
- PCA and SVD are closely related in dimensionality reduction.

## Reference

IBM Machine Learning – Unsupervised Machine Learning, Module 4: Singular Value Decomposition and Dimensionality Reduction Imaging Example.