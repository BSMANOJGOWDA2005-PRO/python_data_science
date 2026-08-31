# Pandas Notes

## 1. What is Pandas?

**Pandas** is a Python library used for **data manipulation, data cleaning, and data analysis**.

It is commonly used in:
- Data Analytics
- Exploratory Data Analysis (EDA)
- Machine Learning
- Data Cleaning

### Interview Definition

> Pandas is a Python library used for data manipulation, data cleaning, and data analysis.

---

## 2. Why Do We Use Pandas?

Suppose we have an `insurance.csv` file:

| age | sex | bmi | charges |
|---:|---|---:|---:|
| 19 | female | 27.9 | 16884 |
| 18 | male | 33.8 | 1725 |
| 28 | male | 33.0 | 4449 |

Instead of manually working with this data, Pandas allows us to easily:

- Read datasets
- View data
- Clean data
- Filter data
- Add/remove columns
- Handle missing values
- Analyze data
- Prepare data for Machine Learning

---

## 3. Import Pandas

```python
import pandas as pd
```

### Why `pd`?

`pd` is the commonly used alias for Pandas.

Instead of:

```python
pandas.read_csv()
```

we normally write:

```python
pd.read_csv()
```

---

# 4. Main Data Structures in Pandas

Pandas mainly has two important data structures:

1. **Series**
2. **DataFrame**

### Series

A Series is **one-dimensional** data.

### DataFrame

A DataFrame is **two-dimensional** data containing rows and columns.

---

# 5. Series

A **Series** is like a single column.

```python
import pandas as pd

data = pd.Series([10, 20, 30, 40])

print(data)
```

Output:

```text
0    10
1    20
2    30
3    40
dtype: int64
```

Here:

```text
0, 1, 2, 3
```

are indexes.

### Series with Custom Index

```python
data = pd.Series(
    [90, 80, 70],
    index=["Maths", "Science", "English"]
)

print(data)
```

---

# 6. DataFrame

A **DataFrame** is a table containing rows and columns.

```python
data = pd.DataFrame({
    "Name": ["Manoj", "Rahul", "Kiran"],
    "Age": [21, 22, 20],
    "Marks": [85, 90, 78]
})

print(data)
```

Output:

```text
    Name  Age  Marks
0  Manoj   21     85
1  Rahul   22     90
2  Kiran   20     78
```

### Easy Definition

> A DataFrame is like an Excel table inside Python.

---

# 7. Reading a CSV File

One of the most important Pandas operations:

```python
data = pd.read_csv("insurance.csv")
```

This loads the CSV file into a DataFrame.

Then:

```python
print(data)
```

or:

```python
data
```

---

# 8. `head()`

`head()` displays the first 5 rows.

```python
data.head()
```

First 10 rows:

```python
data.head(10)
```

### Example

```python
data.head(3)
```

This displays the first 3 rows.

---

# 9. `tail()`

`tail()` displays the last 5 rows.

```python
data.tail()
```

Last 10 rows:

```python
data.tail(10)
```

---

# 10. Shape

`shape` tells us the:

- Number of rows
- Number of columns

```python
data.shape
```

Example:

```text
(123, 4)
```

This means:

```text
123 rows
4 columns
```

### Number of Rows

```python
data.shape[0]
```

### Number of Columns

```python
data.shape[1]
```

---

# 11. Columns

To see the column names:

```python
data.columns
```

Example:

```text
Index(['age', 'sex', 'bmi', 'charges'], dtype='object')
```

Convert columns to a list:

```python
list(data.columns)
```

---

# 12. Index

To see row indexes:

```python
data.index
```

---

# 13. `info()`

`info()` gives information about the dataset.

```python
data.info()
```

It gives:

- Number of rows
- Column names
- Non-null values
- Data types
- Memory usage

Example:

```text
age         123 non-null int64
sex         123 non-null object
bmi         123 non-null float64
charges     123 non-null float64
```

---

# 14. Data Types

Use:

```python
data.dtypes
```

Common data types:

| Type | Meaning |
|---|---|
| `int64` | Integer |
| `float64` | Decimal number |
| `object` | Usually text |
| `bool` | True / False |
| `datetime` | Date and time |

---

# 15. `describe()`

`describe()` gives statistical information.

```python
data.describe()
```

It provides:

- count
- mean
- standard deviation
- minimum
- 25%
- 50%
- 75%
- maximum

Example:

```text
             age         bmi
count      123.0       123.0
mean        35.2        30.5
std         15.4         6.2
min         18.0        15.9
25%         24.0        26.1
50%         34.0        30.2
75%         48.0        34.8
max         64.0        53.1
```

---

# 16. Selecting a Column

Suppose our dataset has:

```text
age
sex
bmi
charges
```

Select one column:

```python
data["age"]
```

You can also use:

```python
data.age
```

### Recommended

```python
data["age"]
```

---

# 17. Selecting Multiple Columns

```python
data[["age", "bmi", "charges"]]
```

### Remember

One column:

```python
data["age"]
```

Multiple columns:

```python
data[["age", "bmi"]]
```

---

# 18. `iloc`

`iloc` means **integer-location based indexing**.

It selects data using the position number.

### First Row

```python
data.iloc[0]
```

### First 5 Rows

```python
data.iloc[0:5]
```

### First Row and First Column

```python
data.iloc[0, 0]
```

### Rows 0–4 and Columns 0–2

```python
data.iloc[0:5, 0:3]
```

---

# 19. `loc`

`loc` is **label-based indexing**.

```python
data.loc[0]
```

Select rows:

```python
data.loc[0:4]
```

Select rows and columns:

```python
data.loc[0:4, ["age", "bmi"]]
```

---

# 20. `loc` vs `iloc`

| `loc` | `iloc` |
|---|---|
| Label-based | Position-based |
| Uses labels | Uses integer positions |
| `data.loc[2]` | `data.iloc[2]` |
| `data.loc[:, "age"]` | `data.iloc[:, 0]` |

### Easy Way to Remember

```text
loc  → label/location
iloc → integer location
```

---

# 21. Filtering Data

Filtering means selecting rows based on a condition.

### Age greater than 30

```python
data[data["age"] > 30]
```

### Age equal to 30

```python
data[data["age"] == 30]
```

### Age less than 30

```python
data[data["age"] < 30]
```

### Age greater than or equal to 30

```python
data[data["age"] >= 30]
```

---

# 22. Multiple Conditions

## AND

Use `&`.

```python
data[(data["age"] > 30) & (data["bmi"] > 25)]
```

Meaning:

> Age greater than 30 AND BMI greater than 25.

## OR

Use `|`.

```python
data[(data["age"] > 30) | (data["bmi"] > 25)]
```

Meaning:

> Age greater than 30 OR BMI greater than 25.

### Important

Always use parentheses around each condition:

```python
(data["age"] > 30)
```

---

# 23. `isin()`

`isin()` checks whether a value exists in a list.

Example:

```python
data[data["age"].isin([20, 30, 40])]
```

Meaning:

> Select rows where age is 20, 30, or 40.

---

# 24. Adding a New Column

Add a column with the same value:

```python
data["new_column"] = 10
```

Every row gets the value `10`.

### Calculated Column

```python
data["bmi_squared"] = data["bmi"] ** 2
```

---

# 25. Removing a Column

```python
data.drop("bmi_squared", axis=1)
```

This returns a new DataFrame.

To permanently remove it:

```python
data.drop("bmi_squared", axis=1, inplace=True)
```

### Axis

```text
axis=0 → rows
axis=1 → columns
```

---

# 26. Removing Rows

Remove row 0:

```python
data.drop(0, axis=0)
```

Remove multiple rows:

```python
data.drop([0, 1, 2], axis=0)
```

---

# 27. Missing Values

Missing data is commonly represented as:

```text
NaN
```

### Check Missing Values

```python
data.isnull()
```

### Count Missing Values

```python
data.isnull().sum()
```

Another method:

```python
data.isna().sum()
```

---

# 28. Removing Missing Values

```python
data.dropna()
```

This removes rows containing missing values.

---

# 29. Filling Missing Values

### Fill with 0

```python
data["age"].fillna(0)
```

### Fill with Mean

```python
data["age"].fillna(data["age"].mean())
```

### Fill with Median

```python
data["age"].fillna(data["age"].median())
```

### Fill with Mode

```python
data["sex"].fillna(data["sex"].mode()[0])
```

---

# 30. Mean, Median and Mode

### Mean

```python
data["age"].mean()
```

### Median

```python
data["age"].median()
```

### Mode

```python
data["age"].mode()
```

These are commonly used when handling missing values.

---

# 31. Duplicate Rows

### Check Duplicates

```python
data.duplicated()
```

### Count Duplicates

```python
data.duplicated().sum()
```

---

# 32. Remove Duplicates

```python
data.drop_duplicates()
```

Permanently:

```python
data.drop_duplicates(inplace=True)
```

---

# 33. Sorting Data

Sort by age:

```python
data.sort_values("age")
```

### Descending Order

```python
data.sort_values("age", ascending=False)
```

### Sort by Multiple Columns

```python
data.sort_values(["age", "bmi"])
```

---

# 34. Unique Values

To find unique values:

```python
data["sex"].unique()
```

Example:

```text
['male' 'female']
```

---

# 35. Number of Unique Values

```python
data["sex"].nunique()
```

This returns the number of unique values.

---

# 36. `value_counts()`

`value_counts()` counts how many times each value occurs.

```python
data["sex"].value_counts()
```

Example:

```text
male      65
female    58
```

This is very useful for categorical data.

---

# 37. Renaming Columns

```python
data.rename(
    columns={"charges": "medical_charges"},
    inplace=True
)
```

Now:

```text
charges
```

becomes:

```text
medical_charges
```

---

# 38. Changing Data Type

Convert to integer:

```python
data["age"] = data["age"].astype(int)
```

Convert to float:

```python
data["age"] = data["age"].astype(float)
```

---

# 39. String Operations

Suppose we have:

```python
data["name"]
```

### Lowercase

```python
data["name"].str.lower()
```

### Uppercase

```python
data["name"].str.upper()
```

### String Length

```python
data["name"].str.len()
```

### Contains

```python
data["name"].str.contains("Manoj")
```

---

# 40. `groupby()`

`groupby()` is very important in data analysis.

Example:

```python
data.groupby("sex")["charges"].mean()
```

Meaning:

> Find the average charges for each sex.

Example result:

```text
sex
female    12500
male      14500
```

---

# 41. GroupBy Multiple Columns

```python
data.groupby(["sex", "smoker"])["charges"].mean()
```

This groups data by both:

- sex
- smoker

Then calculates the average charges.

---

# 42. Aggregation

We can calculate multiple statistics:

```python
data["charges"].agg(["mean", "min", "max", "sum"])
```

For groups:

```python
data.groupby("sex")["charges"].agg(
    ["mean", "min", "max"]
)
```

---

# 43. Reading Excel Files

```python
data = pd.read_excel("data.xlsx")
```

---

# 44. Reading JSON Files

```python
data = pd.read_json("data.json")
```

---

# 45. Saving DataFrame to CSV

```python
data.to_csv("output.csv", index=False)
```

### Why `index=False`?

It prevents Pandas from saving the DataFrame index as an extra column.

---

# 46. Saving DataFrame to Excel

```python
data.to_excel("output.xlsx", index=False)
```

---

# 47. Concatenating DataFrames

`concat()` is used to combine DataFrames.

```python
pd.concat([data1, data2])
```

It is commonly used when adding rows from one DataFrame to another.

---

# 48. Merge

`merge()` is similar to a SQL JOIN.

```python
pd.merge(data1, data2, on="id")
```

### Inner Join

```python
pd.merge(data1, data2, on="id", how="inner")
```

### Left Join

```python
pd.merge(data1, data2, on="id", how="left")
```

### Right Join

```python
pd.merge(data1, data2, on="id", how="right")
```

### Outer Join

```python
pd.merge(data1, data2, on="id", how="outer")
```

---

# 49. Pandas in Machine Learning

A common Machine Learning data workflow is:

```text
Import Libraries
       ↓
Read Dataset
       ↓
Understand Dataset
       ↓
Clean Dataset
       ↓
Handle Missing Values
       ↓
Remove Duplicates
       ↓
Analyze Data
       ↓
Select Features
       ↓
Prepare Data
       ↓
Train Machine Learning Model
```

---

# 50. Basic Pandas Program

```python
import pandas as pd

# Read dataset
data = pd.read_csv("insurance.csv")

# View first rows
print(data.head())

# Check shape
print(data.shape)

# Dataset information
data.info()

# Statistical summary
print(data.describe())

# Check missing values
print(data.isnull().sum())

# Check duplicates
print(data.duplicated().sum())
```

---

# 51. Important Pandas Functions Cheat Sheet

| Function | Purpose |
|---|---|
| `pd.read_csv()` | Read CSV |
| `pd.read_excel()` | Read Excel |
| `pd.read_json()` | Read JSON |
| `data.head()` | First rows |
| `data.tail()` | Last rows |
| `data.shape` | Rows and columns |
| `data.columns` | Column names |
| `data.index` | Row indexes |
| `data.info()` | Dataset information |
| `data.describe()` | Statistical summary |
| `data.dtypes` | Data types |
| `data["column"]` | Select column |
| `data.iloc[]` | Position-based selection |
| `data.loc[]` | Label-based selection |
| `data.isnull()` | Find missing values |
| `data.isnull().sum()` | Count missing values |
| `data.dropna()` | Remove missing rows |
| `data.fillna()` | Fill missing values |
| `data.duplicated()` | Find duplicates |
| `data.drop_duplicates()` | Remove duplicates |
| `data.sort_values()` | Sort data |
| `data.unique()` | Find unique values |
| `data.nunique()` | Number of unique values |
| `data.value_counts()` | Count categories |
| `data.drop()` | Remove rows/columns |
| `data.rename()` | Rename columns |
| `data.groupby()` | Group data |
| `pd.concat()` | Combine DataFrames |
| `pd.merge()` | Join DataFrames |
| `data.to_csv()` | Save CSV |
| `data.to_excel()` | Save Excel |

---

# 52. Most Important Commands to Remember

```python
import pandas as pd

data = pd.read_csv("insurance.csv")

data.head()
data.tail()
data.shape
data.columns
data.info()
data.describe()
data.dtypes

data["age"]
data[["age", "bmi"]]

data.iloc[0]
data.loc[0]

data[data["age"] > 30]

data.isnull().sum()
data.dropna()
data.fillna()

data.duplicated().sum()
data.drop_duplicates()

data["age"].mean()
data["age"].median()
data["age"].mode()

data["sex"].unique()
data["sex"].nunique()
data["sex"].value_counts()

data.sort_values("age")

data.groupby("sex")["charges"].mean()
```

---

# 53. Quick Revision

## Pandas = Load → Look → Clean → Select → Analyze → Save

```text
Load
  ↓
read_csv()

Look
  ↓
head()
info()
describe()

Clean
  ↓
dropna()
fillna()
drop_duplicates()

Select
  ↓
[]
loc[]
iloc[]

Analyze
  ↓
mean()
value_counts()
groupby()

Save
  ↓
to_csv()
```

---

# 54. Interview Questions

### Q1. What is Pandas?

> Pandas is a Python library used for data manipulation, data cleaning, and data analysis.

### Q2. What are the main data structures in Pandas?

> The two main data structures are Series and DataFrame.

### Q3. What is a Series?

> A Series is a one-dimensional labeled data structure.

### Q4. What is a DataFrame?

> A DataFrame is a two-dimensional labeled data structure containing rows and columns.

### Q5. How do you read a CSV file?

```python
pd.read_csv("file.csv")
```

### Q6. How do you check the number of rows and columns?

```python
data.shape
```

### Q7. How do you check missing values?

```python
data.isnull().sum()
```

### Q8. How do you remove duplicate rows?

```python
data.drop_duplicates()
```

### Q9. What is the difference between `loc` and `iloc`?

> `loc` is label-based indexing, while `iloc` is integer-position-based indexing.

### Q10. How do you display statistical information?

```python
data.describe()
```

---

# Final Summary

Pandas is mainly used to **work with tabular data**.

The most important concepts to learn first are:

1. `Series`
2. `DataFrame`
3. `read_csv()`
4. `head()` and `tail()`
5. `shape`
6. `columns`
7. `info()`
8. `describe()`
9. Column selection
10. `loc` and `iloc`
11. Filtering
12. Missing values
13. Duplicates
14. Sorting
15. `groupby()`
16. `value_counts()`
17. `merge()`
18. `concat()`
19. Reading and saving files

**Pandas is one of the most important libraries for Data Analytics, EDA, and Machine Learning.**