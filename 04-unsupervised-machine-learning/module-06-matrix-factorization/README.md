# Module 6 – Matrix Factorization

## Overview

This module introduces Matrix Factorization, with a focus on Non-Negative Matrix Factorization (NMF).

NMF is a dimensionality reduction technique that decomposes a nonnegative data matrix into two smaller nonnegative matrices, commonly represented as W and H.

The technique can be applied to positive-valued data such as word counts in documents and image pixel values.

## Learning Objectives

After completing this module, I should be able to:

- Explain the basic concept of matrix factorization.
- Understand how Non-Negative Matrix Factorization works.
- Explain the roles of matrices W and H.
- Understand how NMF can be applied to document-term matrices.
- Describe how NMF can help identify topics in a collection of documents.
- Understand the relationship between NMF and dimensionality reduction.

## Topics Covered

### 1. Introduction to Matrix Factorization
- Matrix decomposition
- Nonnegative input matrices
- Factor matrices W and H

### 2. Non-Negative Matrix Factorization
- NMF concept
- Nonnegative constraints
- Matrix reconstruction
- Number of components or topics

### 3. NMF for Document and Topic Analysis
- Document-term matrices
- Word counts and term representation
- Topic decomposition
- Interpreting W and H

### 4. Optional Topic
- Term Frequency-Inverse Document Frequency (TF-IDF)

## Module Structure

```text
module-06-matrix-factorization/
├── README.md
├── notes/
│   ├── 01-introduction-to-matrix-factorization.md
│   ├── 02-non-negative-matrix-factorization.md
│   └── 03-nmf-for-document-topic-analysis.md
└── notebooks/
    └── README.md
```

## Key Takeaways

- NMF works with nonnegative input data.
- NMF decomposes an original matrix into two smaller nonnegative matrices.
- W and H represent different parts of the factorization.
- The number of components or topics is selected by the user.
- NMF can be used to discover topic patterns in document collections.
- NMF can also be applied to positive-valued image data.

## Practical Application

One practical application of NMF is topic analysis. A document-term matrix can be decomposed into topic-related representations, helping identify patterns and relationships between words and documents.

## Learning Progress

- [ ] Complete the Matrix Factorization introduction.
- [ ] Study Non-Negative Matrix Factorization.
- [ ] Review the NMF demonstration lab.
- [ ] Complete the NMF practice lab.
- [ ] Review the module summary and quiz.