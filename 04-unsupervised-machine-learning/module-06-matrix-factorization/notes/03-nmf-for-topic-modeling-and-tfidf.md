# NMF for Document and Topic Analysis

## 1. Introduction

Non-Negative Matrix Factorization can be applied to text data to identify topics within a collection of documents.

In this application, text data is first represented as a document-term matrix. NMF then decomposes the matrix into smaller factor matrices that represent relationships between documents, topics, and terms.

## 2. Document-Term Matrix

A document-term matrix is a numerical representation of a collection of documents.

Its structure is:

- Rows represent individual documents.
- Columns represent words or terms.
- Values represent the frequency of a word or another numerical measure of its occurrence in a document.

For example:

| Document | Machine | Learning | Data | Model |
|---|---:|---:|---:|---:|
| Document 1 | 2 | 3 | 1 | 2 |
| Document 2 | 1 | 2 | 3 | 1 |
| Document 3 | 0 | 1 | 2 | 3 |

The values in this matrix are nonnegative, making it suitable for NMF.

## 3. Applying NMF to Documents

NMF decomposes the document-term matrix into two smaller matrices.

Using the conventional document-by-term orientation:

\[
V \approx W \times H
\]

Where:

- **V:** Original document-term matrix.
- **W:** Document-topic matrix.
- **H:** Topic-term matrix.

### 3.1 Matrix W

W describes how strongly each document is associated with each topic.

Each row represents a document, while each column represents a topic.

### 3.2 Matrix H

H describes how strongly each term is associated with each topic.

Each row represents a topic, while each column represents a term.

Together, W and H provide a topic-based representation of the original document collection.

## 4. Understanding Topics

Suppose a document collection contains articles about technology, education, and healthcare.

After applying NMF, the model may identify several groups of terms that frequently occur together.

For example:

| Possible Topic | Example Terms |
|---|---|
| Technology | computer, software, system |
| Education | student, teacher, school |
| Healthcare | patient, hospital, treatment |

These are illustrative examples of how topics may be interpreted. The actual topics depend on the dataset and the selected number of components.

## 5. Choosing the Number of Topics

The number of topics is determined by the user through the number of NMF components.

For example:

```python
from sklearn.decomposition import NMF

nmf = NMF(
    n_components=5,
    random_state=42,
    max_iter=500
)

W = nmf.fit_transform(X)
H = nmf.components_
```

In this example, the model uses five components to represent the document-term matrix.

Choosing a suitable number of topics is important because it affects how the documents are represented.

## 6. Optional: TF-IDF

The course also introduces TF-IDF as an optional topic.

Term Frequency-Inverse Document Frequency (TF-IDF) is a method for representing text numerically by considering how important a term is within a document and across a collection of documents.

A nonnegative TF-IDF matrix can be used as input for NMF.

The input must remain nonnegative to satisfy the NMF requirement.

## 7. NMF Compared with PCA

NMF and Principal Component Analysis (PCA) are both techniques used to represent data through a smaller number of components.

However, they have different characteristics.

| Aspect | NMF | PCA |
|---|---|---|
| Input values | Must be nonnegative | Can contain negative values |
| Components | Nonnegative | Can contain positive and negative values |
| Main idea | Decompose data into nonnegative factors | Find directions that capture variance |
| Example application | Document topic analysis | Dimensionality reduction |

NMF can provide components that are easier to interpret for applications involving word counts and topic representations.

## 8. Key Takeaways

- A document-term matrix represents documents as rows and terms as columns.
- NMF decomposes the matrix into W and H.
- W represents the relationship between documents and topics.
- H represents the relationship between topics and terms.
- The number of topics is selected by the user.
- TF-IDF can be used as an optional text representation when its values are nonnegative.

## 9. Conclusion

NMF provides a way to discover topic patterns in a collection of documents. By decomposing a document-term matrix into document-topic and topic-term representations, it helps simplify text data and reveal relationships between documents and words.