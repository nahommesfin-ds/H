# Data Visualization with Seaborn: Quiz Answers Guide

---

## Question 1: How do you import the Seaborn package?

You import the package by typing:
```python
import seaborn
```

This should be placed **at the top of your Python script**.

**Common convention:**
```python
import seaborn as sns
import matplotlib.pyplot as plt
```

---

## Question 2: How do you create a scatter plot?

You create a scatter plot by typing:
```python
seaborn.scatterplot(data=df, x='x', y='y')
```

**With sns alias:**
```python
sns.scatterplot(data=df, x='x', y='y')
```

**What it does:**
- Shows the relationship between two **continuous variables**
- Each point represents one observation

---

## Question 3: How do you create a line plot?

You create a line plot by typing:
```python
seaborn.lineplot(data=df, x='x', y='y')
```

**With sns alias:**
```python
sns.lineplot(data=df, x='x', y='y')
```

**When to use:**
- Time series data
- Trends over continuous variables
- Showing progression or change

---

## Question 4: How do you create a basic histogram?

You create a basic histogram by typing:
```python
seaborn.histplot(data=df, x='x')
```

**Alternative using displot:**
```python
seaborn.displot(data=df, x='x')
```

**What it shows:**
- The **distribution** of a single variable
- Frequency of values within bins

---

## Question 5: How do you stack data in a histogram?

You stack the data by using the `displot` function and adding the `multiple` argument:
```python
seaborn.displot(data=df, x='x', hue='y', multiple='stack')
```

**Parameters:**
- `hue='y'` - splits data by category
- `multiple='stack'` - stacks the distributions

**Other multiple options:**
- `'layer'` - overlays distributions
- `'dodge'` - places bars side-by-side
- `'fill'` - normalizes to show proportions

---

## Question 6: How do you create a bivariate heat map?

You can create a bivariate heat map by typing:
```python
seaborn.displot(data=df, x='x', y='y', cbar=True)
```

**Parameters:**
- `x='x'` and `y='y'` - two variables
- `cbar=True` - shows the color bar legend

**What it shows:**
- Density of points in 2D space
- Useful for large datasets

---

## Question 7: How do you create a box plot?

You create a box plot by using the `catplot` function and setting the `kind` argument to `box`:
```python
seaborn.catplot(data=df, x='x', y='y', kind='box')
```

**Alternative:**
```python
seaborn.boxplot(data=df, x='x', y='y')
```

**What it shows:**
- Median (middle line)
- Quartiles (box edges)
- Outliers (points beyond whiskers)
- Distribution spread

---

## Question 8: How do you create a violin plot?

You create a violin plot by using the `catplot` function and setting the `kind` argument to `violin`:
```python
seaborn.catplot(data=df, x='x', y='y', kind='violin')
```

**Alternative:**
```python
seaborn.violinplot(data=df, x='x', y='y')
```

**What it shows:**
- Similar to box plot but shows the **full distribution shape**
- Width indicates density of data at different values

---

## Question 9: How do you create a standard bar plot?

You create a standard bar plot by typing:
```python
seaborn.barplot(data=df, x='x', y='y')
```

**Alternative using catplot:**
```python
seaborn.catplot(data=df, x='x', y='y', kind='bar')
```

**What it shows:**
- **Mean** or other aggregate statistic for each category
- Error bars showing confidence intervals

---

## Question 10: How do you add a title to your plot?

You add a title to your plot variable by typing:
```python
ax.set(title='My Title')
```

**Example in context:**
```python
ax = sns.scatterplot(data=df, x='x', y='y')
ax.set(title='My Title')
```

---

## Question 11: How do you save a plot?

Since Seaborn is built on matplotlib, you can save the plot by typing:
```python
pyplot.savefig('output.png')
```

**Or:**
```python
ax.figure.savefig('output.png')
```

**Full example:**
```python
import matplotlib.pyplot as plt
import seaborn as sns

ax = sns.scatterplot(data=df, x='x', y='y')
plt.savefig('output.png')
```

**Common file formats:**
- `.png` - raster image
- `.jpg` - compressed image
- `.pdf` - vector format
- `.svg` - scalable vector

---

## Question 12: How do you label your axes?

You label your axes by typing:
```python
ax.set(xlabel='X Label', ylabel='Y Label')
```

**Example:**
```python
ax = sns.scatterplot(data=df, x='age', y='salary')
ax.set(xlabel='Age (years)', ylabel='Salary ($)')
```

---

## Question 13: How do you change the colors?

You change the colors by adding the `palette` argument inside your plotting function:
```python
sns.scatterplot(data=df, x='x', y='y', palette='Blues')
```

**Built-in palettes:**
- `'Blues'` - blue color scale
- `'Reds'` - red color scale
- `'viridis'` - perceptually uniform
- `'coolwarm'` - diverging colors
- `'Set1'` - categorical colors
- `'husl'` - evenly spaced hues

**View all palettes:**
```python
sns.color_palette()
```

---

## Question 14: How do you change the y-axis to a logarithmic scale?

You can change the y-axis to a logarithmic scale by typing:
```python
ax.set(yscale='log')
```

**Example:**
```python
ax = sns.scatterplot(data=df, x='x', y='y')
ax.set(yscale='log')
```

**Other scale options:**
- `'linear'` - standard scale (default)
- `'log'` - logarithmic scale
- `'symlog'` - symmetric log scale

---

## Question 15: How do you add a linear regression line to a scatter plot?

You can add a linear regression line to a scatter plot by using the `regplot` function:
```python
seaborn.regplot(data=df, x='x', y='y')
```

**What it shows:**
- Scatter plot of data points
- Best-fit **linear regression line**
- Confidence interval (shaded area)

**Remove confidence interval:**
```python
sns.regplot(data=df, x='x', y='y', ci=None)
```

---

## Quick Reference: Seaborn Plot Types

### Relational Plots (Continuous Variables)

| Plot Type | Function | Use Case |
|-----------|----------|----------|
| Scatter plot | `sns.scatterplot()` | Relationship between two variables |
| Line plot | `sns.lineplot()` | Trends over time or continuous variable |
| Regression plot | `sns.regplot()` | Scatter plot with regression line |

### Distribution Plots

| Plot Type | Function | Use Case |
|-----------|----------|----------|
| Histogram | `sns.histplot()` | Distribution of single variable |
| KDE plot | `sns.kdeplot()` | Smooth density estimate |
| Dist plot | `sns.displot()` | Flexible distribution plot |
| Rug plot | `sns.rugplot()` | Individual data points as ticks |

### Categorical Plots

| Plot Type | Function | Use Case |
|-----------|----------|----------|
| Bar plot | `sns.barplot()` | Mean values by category |
| Box plot | `sns.boxplot()` | Distribution summary with quartiles |
| Violin plot | `sns.violinplot()` | Distribution shape by category |
| Strip plot | `sns.stripplot()` | All points in categories |
| Swarm plot | `sns.swarmplot()` | Non-overlapping points |

### Matrix Plots

| Plot Type | Function | Use Case |
|-----------|----------|----------|
| Heatmap | `sns.heatmap()` | 2D matrix with color encoding |
| Cluster map | `sns.clustermap()` | Heatmap with hierarchical clustering |

---

## Quick Reference: Customization Options

### Plot Aesthetics

| Parameter | Example | Description |
|-----------|---------|-------------|
| `palette` | `palette='Blues'` | Color scheme |
| `hue` | `hue='category'` | Color by variable |
| `style` | `style='type'` | Marker style by variable |
| `size` | `size='value'` | Point size by variable |
| `alpha` | `alpha=0.5` | Transparency (0-1) |

### Axis Customization

| Method | Example | Description |
|--------|---------|-------------|
| `ax.set()` | `ax.set(title='Title')` | Set multiple properties |
| `ax.set_xlabel()` | `ax.set_xlabel('X Label')` | Set x-axis label |
| `ax.set_ylabel()` | `ax.set_ylabel('Y Label')` | Set y-axis label |
| `ax.set_title()` | `ax.set_title('Title')` | Set plot title |
| `ax.set_xlim()` | `ax.set_xlim(0, 100)` | Set x-axis limits |
| `ax.set_ylim()` | `ax.set_ylim(0, 100)` | Set y-axis limits |
| `ax.set_xscale()` | `ax.set_xscale('log')` | Set x-axis scale |
| `ax.set_yscale()` | `ax.set_yscale('log')` | Set y-axis scale |

---

## Common Visualization Workflow

**Step 1: Import Libraries**
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
```

**Step 2: Load Data**
```python
df = pd.read_csv('data.csv')
```

**Step 3: Create Plot**
```python
ax = sns.scatterplot(data=df, x='age', y='salary', hue='department')
```

**Step 4: Customize**
```python
ax.set(title='Salary by Age and Department',
       xlabel='Age (years)',
       ylabel='Salary ($)',
       yscale='log')
```

**Step 5: Save**
```python
plt.savefig('salary_plot.png', dpi=300, bbox_inches='tight')
```

---
