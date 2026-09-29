# Pandas Cheatsheet 🐼

A quick reference guide for essential Data Analysis operations in Python using Pandas.

##### [Documentation here 👈](https://pandas.pydata.org/docs/reference/frame.html)

---

## 📑 Table of Contents

* [1. Data Ingestion & Export](#1-data-ingestion--export)
* [2. Exploratory Data Analysis (EDA)](#2-exploratory-data-analysis-eda)
* [3. Data Selection & Filtering](#3-data-selection--filtering)
* [4. Data Cleaning & Transformation](#4-data-cleaning--transformation)
* [5. Aggregation & Grouping](#5-aggregation--grouping)
* [6. Merging & Joining](#6-merging--joining)
* [7. Time Series Operations](#7-time-series-operations)
* [8. Core Object Methods & Built-in Functions Reference](#8-core-object-methods--built-in-functions-reference)
  * [DataFrame Methods](#1-dataframe-methods)
  * [Series Methods](#2-series-methods)
  * [Python Built-in for DataFrame](#3-python-built-in-for-dataframe)
  * [Python Built-in for Series)](#4-python-built-in-for-series)

---

## 1. Data Ingestion & Export

| Action | Code Example |
| :--- | :--- |
| **Read CSV** | `df = pd.read_csv('file.csv', parse_dates=['date_col'])` |
| **Read Excel** | `df = pd.read_excel('file.xlsx', sheet_name='Sheet1')` |
| **Read Parquet** | `df = pd.read_parquet('file.parquet')` |
| **Read SQL Query** | `df = pd.read_sql("SELECT * FROM table", con=engine)` |
| **Export to CSV** | `df.to_csv('output.csv', index=False)` |
| **Export to Excel** | `df.to_excel('output.xlsx', index=False)` |

---

## 2. Exploratory Data Analysis (EDA)

| Action | Code Example |
| :--- | :--- |
| **Inspect Head / Tail** | `df.head(5)` / `df.tail(5)` |
| **DataFrame Overview** | `df.info()` |
| **Summary Statistics** | `df.describe(include='all')` |
| **Shape (Rows, Cols)** | `df.shape` |
| **Column Names** | `df.columns.tolist()` |
| **Value Counts** | `df['col'].value_counts(dropna=False, normalize=True)` |
| **Unique Values** | `df['col'].nunique()` / `df['col'].unique()` |

---

## 3. Data Selection & Filtering

| Action | Code Example |
| :--- | :--- |
| **Select Columns** | `df[['col1', 'col2']]` |
| **Label-based Selection** | `df.loc[0:10, ['col1', 'col2']]` |
| **Index-based Selection** | `df.iloc[0:10, 0:3]` |
| **Single Condition Filter** | `df[df['age'] > 30]` |
| **Multiple Conditions** | `df[(df['age'] > 30) & (df['status'] == 'active')]` |
| **Filter by List** | `df[df['category'].isin(['A', 'B', 'C'])]` |
| **String Pattern Match** | `df[df['name'].str.contains('John', case=False, na=False)]` |

---

## 4. Data Cleaning & Transformation

| Action | Code Example |
| :--- | :--- |
| **Check Missing Values** | `df.isnull().sum()` |
| **Drop Missing Values** | `df.dropna(subset=['critical_col'], inplace=True)` |
| **Fill Missing Values** | `df['col'].fillna(df['col'].median(), inplace=True)` |
| **Rename Columns** | `df.rename(columns={'old_name': 'new_name'}, inplace=True)` |
| **Change Data Types** | `df['col'] = df['col'].astype('category')` |
| **Convert to Datetime** | `df['date'] = pd.to_datetime(df['date'], errors='coerce')` |
| **Drop Duplicates** | `df.drop_duplicates(subset=['id'], keep='last', inplace=True)` |
| **Apply Function** | `df['new_col'] = df['col'].apply(lambda x: x * 2)` |

---

## 5. Aggregation & Grouping

| Action | Code Example |
| :--- | :--- |
| **Basic GroupBy** | `df.groupby('category')['sales'].mean()` |
| **Multiple Aggregations** | `df.groupby('category').agg({'sales': ['sum', 'mean'], 'id': 'count'})` |
| **Pivot Table** | `pd.pivot_table(df, values='sales', index='region', columns='year', aggfunc='sum')` |
| **Cumulative Sum** | `df['cum_sales'] = df.groupby('region')['sales'].cumsum()` |

---

## 6. Merging & Joining

| Action | Code Example |
| :--- | :--- |
| **Inner / Left Join** | `pd.merge(df1, df2, on='key', how='left')` |
| **Join on Different Keys** | `pd.merge(df1, df2, left_on='id', right_on='user_id', how='inner')` |
| **Concatenate Rows** | `pd.concat([df1, df2], axis=0, ignore_index=True)` |
| **Concatenate Columns** | `pd.concat([df1, df2], axis=1)` |

---

## 7. Time Series Operations

| Action | Code Example |
| :--- | :--- |
| **Set Datetime Index** | `df.set_index('date', inplace=True)` |
| **Resample (e.g., Monthly)** | `df.resample('ME')['sales'].sum()` |
| **Shift / Lag Values** | `df['prev_sales'] = df['sales'].shift(1)` |
| **Rolling Window** | `df['rolling_7d'] = df['sales'].rolling(window=7).mean()` |

---

## 8. Core Object Methods & Built-in Functions Reference

### 1. DataFrame Methods

| Method Name | Main Purpose |
| :--- | :--- |
| `head()`, `tail()`, `info()`, `describe()` | View structure, summary statistics, and rows |
| `dropna()`, `fillna()`, `drop_duplicates()` | Clean missing values and drop duplicates |
| `sort_values()`, `sort_index()` | Sort DataFrame by values or index |
| `loc[]`, `iloc[]`, `query()` | Selection, indexing, and filtering |
| `set_index()`, `reset_index()` | Modify index structure |
| `groupby()`, `merge()`, `join()`, `concat()` | Grouping, aggregation, and table joins |
| `pivot_table()`, `melt()` | Reshape tables (wide/long) |
| `astype()` | Convert column data types |
| `agg()` | Apply multiple aggregation functions |

### 2. Series Methods

| Method Name | Main Purpose |
| :--- | :--- |
| `unique()`, `nunique()`, `value_counts()` | Get unique elements and frequency counts |
| `dropna()`, `fillna()`, `drop_duplicates()` | Clean missing values and drop duplicates |
| `sort_values()`, `sort_index()` | Sort Series |
| `str.*`, `dt.*`, `map()`, `apply()` | Vectorized string/date operations and mapping |
| `nlargest()`, `nsmallest()` | Get top/bottom $N$ elements |
| `shift()`, `diff()`, `rolling()`, `rank()` | Window, lag, and ranking calculations |
| `transform()` | Broadcast aggregated results back to original shape |

### 3. Python Built-in for DataFrame

| Built-in Function | Behavior on DataFrame |
| :--- | :--- |
| `len()` | Returns the number of rows |
| `type()` | Returns `<class 'pandas.core.frame.DataFrame'>` |
| `print()` / `str()` | Converts to a table-formatted string |
| `iter()` / `for` | Iterates over column names |
| `abs()` / `round()` | Applies absolute value/rounding to all numeric columns |

### 4. Python Built-in for Series

| Built-in Function | Behavior on Series |
| :--- | :--- |
| `len()` | Returns the element count (length) |
| `type()` | Returns `<class 'pandas.core.series.Series'>` |
| `print()` / `str()` | Converts to a list-formatted string |
| `iter()` / `for` | Iterates over element values |
| `abs()` / `round()` | Applies absolute value/rounding to all numeric elements |
