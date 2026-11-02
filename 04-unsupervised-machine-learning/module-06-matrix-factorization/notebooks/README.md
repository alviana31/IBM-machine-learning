# Module 6 – Notebooks

This folder contains practical notebooks related to Matrix Factorization and Non-Negative Matrix Factorization (NMF).

## Suggested Notebook Activities

### 1. NMF Demonstration Lab
- Prepare a nonnegative input matrix.
- Import NMF from Scikit-learn.
- Set the number of components.
- Fit and transform the input data.
- Examine the W and H matrices.
- Reconstruct an approximation of the original matrix.

### 2. NMF Practice Lab
- Apply NMF to a document-term matrix.
- Explore the relationship between documents, topics, and terms.
- Experiment with different numbers of components.
- Interpret the resulting topic representations.

### 3. Optional: TF-IDF
- Convert text documents into TF-IDF representations.
- Check that the resulting values are nonnegative.
- Apply NMF to the transformed text data.

## Important Notes

- NMF requires nonnegative input data.
- The number of components must be selected before fitting the model.
- W and H are both nonnegative matrices.
- The product of W and H approximates the original matrix.
- Interpret topics based on the terms and document patterns produced by the model.

## Notebook Status

- [ ] NMF Demonstration Lab
- [ ] NMF Practice Lab
- [ ] Optional TF-IDF Practice