# Retrieving Data from CSV and JSON Files

## 1. Introduction

Data retrieval is the process of collecting or accessing data from different sources so it can be used for analysis and Machine Learning.

Two common file formats used to store data are CSV and JSON.

## 2. CSV (Comma-Separated Values)

CSV is a text-based file format used to store tabular data. Each row represents an observation, while commas are commonly used to separate values between columns.

**Example:**

```csv
name,age,score
Alice,20,85
Bob,21,90
Charlie,19,88
```

### Reading CSV with Pandas

```python
import pandas as pd

df = pd.read_csv("data.csv")

print(df.head())
```

The `read_csv()` function loads CSV data into a Pandas DataFrame.

## 3. JSON (JavaScript Object Notation)

JSON is a standard data format used to store and exchange structured information across different platforms.

Its structure is similar to Python dictionaries.

**Example:**

```json
{
    "name": "Alice",
    "age": 20,
    "score": 85
}
```

### Reading JSON with Pandas

```python
import pandas as pd

df = pd.read_json("data.json")

print(df.head())
```

### Exporting Data to JSON

```python
df.to_json("output.json", orient="records", indent=4)
```

## 4. CSV vs JSON

| Aspect | CSV | JSON |
|---|---|---|
| Structure | Tabular | Key-value and nested structures |
| Common use | Spreadsheet data | Data exchange |
| Read with Pandas | `read_csv()` | `read_json()` |

## 5. Key Takeaways

- CSV is commonly used for tabular data.
- JSON supports structured data and nested objects.
- Pandas provides functions to read both formats.