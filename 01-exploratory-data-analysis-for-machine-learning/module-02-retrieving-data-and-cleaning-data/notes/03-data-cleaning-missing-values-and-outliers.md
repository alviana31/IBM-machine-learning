# Data Cleaning: Missing Values and Outliers

## 1. Introduction

Data cleaning is the process of identifying and handling problems in a dataset before it is used for analysis or Machine Learning.

Messy data can lead to unreliable results.

## 2. Common Data Quality Problems

Some common problems include:

- Duplicate or unnecessary data.
- Inconsistent values and typing errors.
- Missing data.
- Outliers.
- Problems originating from data sources.

## 3. Handling Duplicate Data

Duplicate data refers to records that appear more than once in a dataset.

Duplicates should be identified to prevent unnecessary or repeated information from affecting analysis.

Example:

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.duplicated().sum())
```

Remove duplicate rows:

```python
df = df.drop_duplicates()
```

## 4. Handling Missing Values

Missing values occur when some observations do not contain information for particular features or labels.

Common approaches include:

### 4.1 Removing Rows or Columns

Remove observations or columns that contain missing values when appropriate.

```python
df = df.dropna()
```

### 4.2 Imputation

Imputation means replacing missing values with estimated or selected values.

Example using the mean:

```python
df["age"] = df["age"].fillna(df["age"].mean())
```

### 4.3 Masking Missing Values

Missing values can also be represented using a separate category.

This approach can be useful when the absence of information itself is meaningful.

## 5. Handling Outliers

Outliers are observations that differ significantly from the general pattern of the dataset.

Outliers may affect statistical analysis and Machine Learning results.

### 5.1 Identifying Outliers

The course introduces several approaches:

- Plots.
- Statistical methods.
- Residuals.

### 5.2 Handling Outliers

Possible approaches include:

- Removing outliers.
- Imputing unusual values.
- Applying variable transformations.
- Using models that are resistant to outliers.

## 6. Outliers and Residuals

Residuals are differences between observed values and values predicted by a model.

They can be examined to help identify observations that do not follow the expected pattern.

Residual analysis is one of the approaches introduced in the course for examining unusual data.

## 7. Importance of Data Cleaning

Data cleaning helps improve data quality before the dataset is used in further analysis.

However, not every missing value or outlier should automatically be removed.

The chosen treatment should consider the characteristics and context of the data.

## Key Takeaways

- Messy data can produce unreliable outcomes.
- Missing values can be removed, imputed, or masked.
- Outliers can be identified through plots, statistics, and residuals.
- Outliers can be removed, imputed, transformed, or handled using resistant models.
- Data cleaning is an important preparation step in Machine Learning.