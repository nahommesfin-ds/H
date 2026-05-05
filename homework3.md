# Python and Pandas Quiz: Answers Guide

---

## Question 1: How do you import the pandas library?

You import the pandas library by typing:
```python
import pandas as pd
```

This should be placed **at the start of your code**.

---

## Question 2: How do you read a CSV file?

You read the file by using the command:
```python
pd.read_csv('data.csv')
```

**Note:** Replace `'data.csv'` with your actual filename.

---

## Question 3: How do you see the first five rows of a DataFrame?

You can see the first five rows by using the command:
```python
df.head()
```

**What it does:**
- Displays the **top 5 rows** by default
- Useful for quick data inspection

---

## Question 4: How do you find the number of rows and columns?

You use the **shape attribute** by typing:
```python
df.shape
```

**Output format:** `(rows, columns)`

**Example:** `(100, 5)` means 100 rows and 5 columns

---

## Question 5: How do you print the column names?

You can print the column names by using the command:
```python
df.columns
```

---

## Question 6: How do you check data types and missing values?

### Check Data Types
```python
df.dtypes
```

This shows the **data type for each column** (e.g., int64, float64, object)

### Count Missing Values
```python
df.isna().sum()
```

This counts the **number of missing values** in each column

---

## Question 7: How do you select rows where column A is greater than 5?

You can select those specific rows by typing:
```python
df.loc[df.A > 5]
```

**Breakdown:**
- `df.A > 5` creates a **boolean condition**
- `df.loc[]` filters rows based on that condition

---

## Question 8: How do you select multiple columns?

You can select multiple columns by putting their names in a **list**:
```python
df[['A', 'B']]
```

**Important:** Note the **double square brackets** `[[]]`

---

## Question 9: How do you rename a column?

You use the **rename method**. A clean way to write this in Python is:
```python
df.rename(columns=dict(A='Alpha'), inplace=True)
```

**Parameters:**
- `columns=dict(A='Alpha')` maps old name → new name
- `inplace=True` modifies the DataFrame directly

**Alternative syntax:**
```python
df.rename(columns={'A': 'Alpha'}, inplace=True)
```

---

## Question 10: How do you handle specific values as missing (e.g., 999)?

### Method 1: Set na_values when importing
```python
pd.read_csv('data.csv', na_values=999)
```

This treats **999 as NaN** during import.

### Method 2: Replace values after import
```python
df.replace(999, np.nan, inplace=True)
```

---

## Question 11: How do you remove rows with missing values?

You can remove those rows entirely by using the command:
```python
df.dropna()
```

**What it does:**
- Removes **any row** containing at least one missing value
- Returns a new DataFrame (unless `inplace=True`)

---

## Question 12: How do you fill missing values with zero?

You can fill all of the missing values with zero by using the command:
```python
df.fillna(0)
```

**Variations:**
- `df.fillna(method='ffill')` - forward fill
- `df.fillna(method='bfill')` - backward fill
- `df.fillna(df.mean())` - fill with column mean

---

## Question 13: How do you calculate the average of a column?

You calculate the average by typing:
```python
df.A.mean()
```

**Alternative syntax:**
```python
df['A'].mean()
```

---

## Question 14: How do you create a new column from existing columns?

You can create the new column by typing:
```python
df['C'] = df.A + df.B
```

**What it does:**
- Creates a **new column C**
- Contains the **sum** of columns A and B

**Other operations:**
- Subtraction: `df['C'] = df.A - df.B`
- Multiplication: `df['C'] = df.A * df.B`
- Division: `df['C'] = df.A / df.B`

---

## Question 15: How do you save a DataFrame to a CSV file?

According to the pandas documentation, you can save the dataframe to a new file by typing:
```python
df.to_csv('output.csv')
```

**Optional parameters:**
- `index=False` - don't save row indices
- `sep='\t'` - use tab separator instead of comma
- `encoding='utf-8'` - specify character encoding

---

## Quick Reference Cheat Sheet

### Data Import and Inspection

| Task | Command |
|------|---------|
| Import pandas | `import pandas as pd` |
| Read CSV | `pd.read_csv('file.csv')` |
| View first rows | `df.head()` |
| View last rows | `df.tail()` |
| DataFrame shape | `df.shape` |
| Column names | `df.columns` |
| Data types | `df.dtypes` |
| Summary statistics | `df.describe()` |

### Data Selection and Filtering

| Task | Command |
|------|---------|
| Select column | `df['A']` or `df.A` |
| Select multiple columns | `df[['A', 'B']]` |
| Filter rows | `df.loc[df.A > 5]` |
| Select by position | `df.iloc[0:5]` |

### Data Cleaning

| Task | Command |
|------|---------|
| Count missing values | `df.isna().sum()` |
| Drop missing values | `df.dropna()` |
| Fill missing values | `df.fillna(0)` |
| Replace values | `df.replace(999, np.nan)` |
| Rename columns | `df.rename(columns={'A': 'Alpha'})` |

### Data Manipulation

| Task | Command |
|------|---------|
| Calculate mean | `df.A.mean()` |
| Calculate sum | `df.A.sum()` |
| Calculate median | `df.A.median()` |
| Create new column | `df['C'] = df.A + df.B` |

### Data Export

| Task | Command |
|------|---------|
| Save to CSV | `df.to_csv('output.csv')` |
| Save without index | `df.to_csv('output.csv', index=False)` |

---

## Practice Tips

**Best Practices:**
1. Always start with `import pandas as pd`
2. Use `df.head()` to inspect data after loading
3. Check for missing values with `df.isna().sum()`
4. Use `inplace=True` sparingly (makes debugging harder)
5. Save your work frequently with `to_csv()`

**Common Mistakes to Avoid:**
- Forgetting double brackets for multiple columns: `df[['A', 'B']]`
- Not assigning results back: `df = df.dropna()`
- Confusing `.loc[]` (label-based) with `.iloc[]` (position-based)

---
