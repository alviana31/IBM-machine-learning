# Introduction to Matrix Factorization

## 1. Definition

Matrix Factorization is a technique used to decompose an original matrix into two or more smaller matrices.

The purpose is to represent the original data in a simpler form while preserving important information or patterns.

One application of matrix factorization is identifying hidden structures in data, including patterns in text documents.

## 2. Basic Concept

In general, matrix factorization represents an original matrix as a product of smaller matrices.

For example:

\[
V \approx W \times H
\]

Where:

- **V**: Original data matrix.
- **W**: First factor matrix.
- **H**: Second factor matrix.

The factor matrices represent the original data using a different structure.

## 3. Non-Negative Data

The course focuses on decomposing matrices containing only positive values.

Examples include:

- Word counts in documents.
- Pixel intensity values in images.

This leads to Non-Negative Matrix Factorization (NMF), where the original matrix and its factor matrices contain non-negative values.

## 4. Applications

Matrix factorization can be applied to different types of data, including:

- Text analysis.
- Image processing.
- Pattern identification.
- Topic modeling.

## 5. Key Takeaways

- Matrix factorization decomposes a matrix into smaller matrices.
- The decomposition can help reveal hidden patterns in data.
- NMF is a matrix factorization method that uses non-negative values.
- The number of components can be selected based on the analysis objective.