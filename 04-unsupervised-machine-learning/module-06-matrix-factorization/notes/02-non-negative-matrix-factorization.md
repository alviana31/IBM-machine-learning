# Non-Negative Matrix Factorization (NMF)

## 1. Definition

Non-Negative Matrix Factorization (NMF) is a matrix decomposition technique that breaks down an original matrix into two smaller matrices, where all values in the matrices are non-negative.

Unlike methods that can work with negative values, NMF requires the input data to contain only non-negative values.

## 2. Mathematical Representation

NMF approximates the original matrix using:

\[
V \approx W \times H
\]

For a document-term matrix using the Scikit-learn convention:

- **V**: Original document-term matrix.
- **W**: Document-topic matrix.
- **H**: Topic-term matrix.

If the original matrix has dimensions:

\[
V \in \mathbb{R}^{m \times n}
\]

Then the factor matrices can have dimensions:

\[
W \in \mathbb{R}^{m \times k}
\]

\[
H \in \mathbb{R}^{k \times n}
\]

Where:

- \(m\) represents the number of documents.
- \(n\) represents the number of terms.
- \(k\) represents the number of selected components or topics.

All values in V, W, and H must be non-negative.

## 3. How NMF Works

The general process is:

1. Prepare a non-negative input matrix.
2. Select the number of components or topics.
3. Decompose the original matrix into W and H.
4. Interpret the patterns represented by the resulting matrices.
5. Use the factor matrices to approximate the original data.

## 4. Selecting the Number of Components

The number of components is selected by the user.

In topic modeling, the selected components can represent the topics that appear in the documents.

Choosing the number of components is similar to selecting the number of components when applying PCA.

## 5. NMF with Scikit-learn

Example implementation:

```python
from sklearn.decomposition import NMF

nmf = NMF(
    n_components=5,
    random_state=42,
    max_iter=500
)

W = nmf.fit_transform(X)
H = nmf.components_

X_approx = W @ H
```

Explanation:

- `n_components=5`: Defines the number of components.
- `fit_transform(X)`: Fits the NMF model and returns the document-component matrix.
- `components_`: Stores the component-term matrix.
- `W @ H`: Reconstructs an approximation of the original matrix.

The input matrix `X` must contain non-negative values.

## 6. Key Takeaways

- NMF decomposes an original non-negative matrix into two non-negative matrices.
- The decomposition is represented as \(V \approx W \times H\).
- The number of components is determined by the user.
- NMF can help identify meaningful patterns in text and image data.