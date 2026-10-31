# Retrieving Data from Databases, APIs, and Cloud

## 1. Introduction

Data can be retrieved from different sources, including databases, APIs, and cloud services.

This section introduces SQL databases, NoSQL databases, APIs, and cloud data sources.

## 2. SQL Databases

SQL databases store data in relational tables with a fixed schema.

Data can be retrieved using SQL queries.

Example:

```sql
SELECT * FROM employees;
```

### Reading Database Files with SQLite and Pandas

The general process includes:

1. Define the database file path.
2. Create a connection to the database.
3. Prepare an SQL query.
4. Read the query result using Pandas.
5. Inspect the available database tables.

Example:

```python
import sqlite3
import pandas as pd

database_path = "company.db"

connection = sqlite3.connect(database_path)

query = "SELECT * FROM employees"

observations = pd.read_sql(query, connection)

print(observations.head())

connection.close()
```

## 3. NoSQL Databases

NoSQL databases are non-relational databases. Their structures can vary and are not limited to traditional relational tables.

Many NoSQL databases store data using JSON-like formats.

## 4. APIs

An Application Programming Interface (API) allows different software applications to communicate and exchange data.

APIs can be used as a source of data for analysis.

## 5. Cloud Data Sources

Cloud platforms provide access to data stored and managed through online infrastructure.

They allow users to access data without relying only on local storage.

## Key Takeaways

- SQL databases use relational structures and fixed schemas.
- NoSQL databases use more flexible data structures.
- APIs enable data exchange between applications.
- Cloud services provide remote data storage and access.
- SQLite and Pandas can be used to retrieve database data.