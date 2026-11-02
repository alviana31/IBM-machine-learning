# Introduction to Matrix Factorization

## 1. Introduction

Matrix Factorization is a technique that decomposes an original matrix into smaller matrices.

The purpose is to represent the original data using a different structure that can reveal patterns or simplify the representation of the data.

In this module, the main focus is Non-Negative Matrix Factorization (NMF).

## 2. Matrix Decomposition

A matrix contains values arranged in rows and columns.

Matrix factorization attempts to represent an original matrix using two or more smaller matrices.

For NMF, the original matrix is decomposed into two matrices, W and H.

Both resulting matrices contain only nonnegative values.

## 3. Nonnegative Data

NMF requires the input matrix to contain nonnegative values.

Examples of data that can be represented using nonnegative values include:

- Word counts in documents.
- Image pixel values.
- Other numerical data that does not contain negative values.

This requirement distinguishes NMF from some other dimensionality reduction techniques.

## 4. Why Use Matrix Factorization?

Matrix factorization can help represent complex data using a smaller number of components.

For example, a collection of documents may contain thousands of different words. Instead of working directly with every word, NMF can represent the documents through a smaller set of topics.

This can make it easier to identify patterns in the data.

## 5. Relationship to Dimensionality Reduction

NMF is related to dimensionality reduction because the original data can be represented using a smaller number of components.

The number of components is selected by the user.

In document analysis, these components can be interpreted as topics that help describe the documents.

## 6. Key Takeaways

- Matrix factorization decomposes an original matrix into smaller matrices.
- NMF uses nonnegative input values.
- The resulting factor matrices are also nonnegative.
- The technique can help identify patterns and reduce the representation of data.
- NMF can be applied to word counts and image pixel values.

## 7. Conclusion

Matrix factorization provides a way to represent data through smaller matrices. NMF applies this idea to nonnegative data and is useful for applications such as document analysis and topic identification.