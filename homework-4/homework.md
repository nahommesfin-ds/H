# Exploratory Data Analysis (EDA) Quiz: Answers Guide

---

## Question 1: How do you import the pandas package?

You import the package by typing:
```python
import pandas as pd
```

This should be placed **at the top of your code**.

---

## Question 2: How do you load a CSV file into your notebook?

You use the `pd.read_csv()` function to load the file:
```python
df = pd.read_csv('filename.csv')
```

**Remember:** Replace `'filename.csv'` with your actual file name.

---

## Question 3: How do you display the top five rows?

You display the top five rows by typing:
```python
df.head()
```

**What it does:**
- Shows the **first 5 rows** of your DataFrame
- Great for quick data inspection

---

## Question 4: How do you calculate the average age?

You calculate the average age by typing:
```python
df.Age.mean()
```

**Alternative syntax:**
```python
df['Age'].mean()
```

---

## Question 5: How do you find the middle salary value (median)?

You find the middle salary value by typing:
```python
df.Salary.median()
```

**What is median?**
- The **middle value** when data is sorted
- Less affected by outliers than the mean

---

## Question 6: How do you find the standard deviation?

You find the standard deviation by typing:
```python
df.Score.std()
```

**What is standard deviation?**
- Measures how **spread out** the values are
- Higher value = more variation in the data

---

## Question 7: How do you count all missing values across columns?

You count all the missing values across columns by typing:
```python
df.isna().sum()
```

**Output:** Shows the count of missing values for **each column**

**Alternative:**
```python
df.isnull().sum()  # Same as isna()
```

---

## Question 8: How do you find how two variables relate to each other?

You find how the two variables relate to each other by typing:
```python
df.Age.corr(df['Salary'])
```

**What is correlation?**
- Ranges from **-1 to 1**
- **1** = perfect positive relationship
- **-1** = perfect negative relationship
- **0** = no linear relationship

---

## Question 9: How do you filter for people older than 30?

You filter for people older than 30 by typing:
```python
df.loc[df.Age > 30]
```

**How it works:**
- `df.Age > 30` creates a **boolean filter**
- `df.loc[]` selects rows where the condition is True

**Other comparison operators:**
- `>=` greater than or equal
- `<` less than
- `<=` less than or equal
- `==` equal to
- `!=` not equal to

---

## Question 10: How do you find the range (difference between max and min)?

You subtract the lowest score from the highest score by typing:
```python
df.Score.max() - df.Score.min()
```

**Breakdown:**
- `df.Score.max()` finds the highest score
- `df.Score.min()` finds the lowest score
- Subtraction gives you the **range**

---

## Question 11: How do you group data and calculate the average?

You group the data and calculate the average by typing:
```python
df.groupby('Department').Salary.mean()
```

**What it does:**
- Groups rows by **Department**
- Calculates the **average Salary** for each group

**Other aggregation functions:**
- `.sum()` - total
- `.count()` - number of items
- `.min()` - minimum value
- `.max()` - maximum value

---

## Question 12: How do you group by multiple columns?

You group by multiple columns using a **list** and count them like this:
```python
df.groupby(['Department', 'Job Title']).size()
```

**What it does:**
- Groups by both **Department** and **Job Title**
- `.size()` counts the number of rows in each group

**Alternative for counting:**
```python
df.groupby(['Department', 'Job Title']).count()
```

---

## Question 13: How do you find the highest age per department?

You find the highest age per department by typing:
```python
df.groupby('Department').Age.max()
```

**Output:** Shows the **maximum age** in each department

---

## Question 14: How do you create a simple contingency table?

You create a simple contingency table by typing:
```python
pd.crosstab(df.Department, df['Job Title'])
```

**What is a contingency table?**
- Shows the **frequency distribution** of two categorical variables
- Also called a **cross-tabulation** or **pivot table**

---

## Question 15: How do you get the average salary in a crosstab?

You add a few extra arguments to the crosstab function to get the average salary like this:
```python
pd.crosstab(df.Department, df['Job Title'], values=df.Salary, aggfunc='mean')
```

**Parameters:**
- `values=df.Salary` - the column to aggregate
- `aggfunc='mean'` - the aggregation function (average)

**Other aggregation functions:**
- `'sum'` - total
- `'median'` - middle value
- `'min'` - minimum
- `'max'` - maximum
- `'count'` - number of entries

---

## Quick Reference: Statistical Functions

### Descriptive Statistics

| Function | Command | Description |
|----------|---------|-------------|
| Mean (average) | `df.Column.mean()` | Average value |
| Median (middle) | `df.Column.median()` | Middle value |
| Mode (most common) | `df.Column.mode()` | Most frequent value |
| Standard deviation | `df.Column.std()` | Spread of data |
| Variance | `df.Column.var()` | Squared std deviation |
| Minimum | `df.Column.min()` | Smallest value |
| Maximum | `df.Column.max()` | Largest value |
| Sum | `df.Column.sum()` | Total of all values |
| Count | `df.Column.count()` | Number of non-null values |

---

## Quick Reference: Data Analysis Functions

### Missing Values

| Task | Command |
|------|---------|
| Count missing values | `df.isna().sum()` |
| Check if any missing | `df.isna().any()` |
| Check if all missing | `df.isna().all()` |
| Drop missing values | `df.dropna()` |
| Fill missing values | `df.fillna(0)` |

### Filtering and Selection

| Task | Command |
|------|---------|
| Filter rows | `df.loc[df.Age > 30]` |
| Multiple conditions (AND) | `df.loc[(df.Age > 30) & (df.Salary > 50000)]` |
| Multiple conditions (OR) | `df.loc[(df.Age > 30) \| (df.Salary > 50000)]` |
| Filter by list | `df.loc[df.Department.isin(['Sales', 'IT'])]` |

### Grouping and Aggregation

| Task | Command |
|------|---------|
| Group by one column | `df.groupby('Department').Salary.mean()` |
| Group by multiple columns | `df.groupby(['Dept', 'Title']).Salary.mean()` |
| Count group sizes | `df.groupby('Department').size()` |
| Multiple aggregations | `df.groupby('Dept').agg({'Salary': 'mean', 'Age': 'max'})` |

### Correlation and Relationships

| Task | Command |
|------|---------|
| Correlation between two columns | `df.Column1.corr(df.Column2)` |
| Correlation matrix | `df.corr()` |
| Covariance | `df.Column1.cov(df.Column2)` |

### Cross-Tabulation

| Task | Command |
|------|---------|
| Simple crosstab | `pd.crosstab(df.Col1, df.Col2)` |
| Crosstab with values | `pd.crosstab(df.Col1, df.Col2, values=df.Col3, aggfunc='mean')` |
| Crosstab with margins | `pd.crosstab(df.Col1, df.Col2, margins=True)` |
| Crosstab with percentages | `pd.crosstab(df.Col1, df.Col2, normalize='all')` |

---

## Common EDA Workflow

**Step 1: Load and Inspect**
```python
import pandas as pd
df = pd.read_csv('data.csv')
df.head()
df.shape
df.info()
```

**Step 2: Check Data Quality**
```python
df.isna().sum()
df.duplicated().sum()
df.dtypes
```

**Step 3: Descriptive Statistics**
```python
df.describe()
df.Column.mean()
df.Column.median()
df.Column.std()
```

**Step 4: Explore Relationships**
```python
df.Column1.corr(df.Column2)
df.groupby('Category').Value.mean()
pd.crosstab(df.Cat1, df.Cat2)
```

**Step 5: Filter and Analyze**
```python
df.loc[df.Age > 30]
df.groupby('Department').Salary.agg(['mean', 'median', 'std'])
```

---
