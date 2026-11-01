# NMF for Topic Modeling and TF-IDF

## 1. Document-Term Matrix

A document-term matrix is a representation of text data in the form of a matrix.

Its structure consists of:

- Rows representing individual documents.
- Columns representing words or terms.
- Values representing word counts or another measure of word occurrence in each document.

Example:

| Document | Data | Machine | Learning |
|---|---:|---:|---:|
| Document 1 | 3 | 2 | 1 |
| Document 2 | 1 | 1 | 4 |
| Document 3 | 0 | 3 | 2 |

This matrix can be used as input for NMF because its values are non-negative.

## 2. NMF for Topic Modeling

NMF can be used to identify topics within a collection of documents.

The decomposition produces two matrices:

### W – Document-Topic Matrix

W represents the relationship between documents and topics.

Each value indicates how strongly a document is associated with a particular topic.

### H – Topic-Term Matrix

H represents the relationship between topics and terms.

The values indicate how strongly a word contributes to a particular topic.

Together, W and H can be used to approximate the original document-term matrix.

**Note:** Matrix orientation and naming can vary depending on the implementation. This documentation follows the Scikit-learn convention, where W represents documents-to-topics and H represents topics-to-terms.

## 3. Understanding Topics

After applying NMF, the terms with the highest weights in each component can be examined to understand the topic represented by that component.

For example, a component containing words such as:

- computer
- software
- programming
- algorithm

may represent a topic related to computer science.

The topic interpretation depends on the input documents and the resulting word weights.

## 4. TF-IDF

TF-IDF stands for Term Frequency–Inverse Document Frequency.

It is a method for weighting words in a text collection.

TF-IDF considers:

- **Term Frequency (TF):** How frequently a term appears in a document.
- **Inverse Document Frequency (IDF):** How informative a term is across the document collection.

TF-IDF can reduce the influence of terms that appear frequently across many documents and give more weight to terms that are more distinctive.

TF-IDF is a text representation and weighting method, not a matrix factorization algorithm.

Its output can be used as input to NMF when the resulting matrix is non-negative.

## 5. Example Using Scikit-learn

```python
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.decomposition import NMF

documents = [
    "Machine learning studies data and algorithms",
    "Deep learning uses neural networks",
    "Programming helps develop software applications"
]

vectorizer = TfidfVectorizer()
X = vectorizer.fit_transform(documents)

nmf = NMF(
    n_components=2,
    random_state=42,
    max_iter=500
)

W = nmf.fit_transform(X)
H = nmf.components_
```

In this example:

1. Documents are converted into numerical features using TF-IDF.
2. NMF decomposes the resulting non-negative matrix.
3. W represents document-topic relationships.
4. H represents topic-term relationships.

## 6. Key Takeaways

- A document-term matrix represents documents and their terms numerically.
- NMF can discover topics by decomposing a document-term matrix.
- W represents document-topic relationships in the Scikit-learn convention.
- H represents topic-term relationships.
- TF-IDF is used to weight text features and can provide non-negative input for NMF.