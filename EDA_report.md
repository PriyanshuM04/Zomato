# EDA Report — Zomato Data

**Dataset:** Zomato data .csv

**Date:** 2025-12-25

## Summary
- Performed basic cleaning and exploratory plots to understand restaurant types, ratings, votes, and ordering behavior.

## Data Loading
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("Zomato data .csv")
```

## Data Cleaning
Converted `rate` values (strings like '4.1/5') to floats:

```python
def handle_rate(value):
    value = str(value).split('/')
    value = value[0]
    return float(value)

df['rate'] = df['rate'].apply(handle_rate)
```

## Inspection
- `df.head()` — quick preview of rows.
- `df.info()` — data types and non-null counts.

**Conclusion:** There are NO NULL values (per notebook inspection).

## Key Analyses & Findings

### Type of Restaurant
Code used:
```python
sns.countplot(x = df['listed_in(type)'])
plt.xlabel("Type of Restaurant")
```
Finding: Dining restaurants are preferred by a larger number of customers.

### Votes by Type
Code used:
```python
grouped_data = df.groupby("listed_in(type)")["votes"].sum()
result = pd.DataFrame({"votes" : grouped_data})
plt.plot(result, c = "green", marker = "o")
plt.xlabel("Type of Restaurant", c = "red", size = 15)
plt.ylabel("Votes", c = "red", size = 15)
```
Finding: Visualized total votes per restaurant type (line plot).

### Rating Distribution
Code used:
```python
plt.hist(df["rate"], bins = 5)
plt.title("Rating Distribution")
plt.show()
```
Finding: Majority of restaurants have ratings between 3.5 and 4.

### Approximate Cost (for two)
Code used:
```python
couple_data = df['approx_cost(for two people)']
sns.countplot(x = couple_data)
```
Finding: Most couples prefer restaurants with approximate cost around 300 rupees.

### Online Order vs Rating
Code used:
```python
plt.figure(figsize = (6, 6))
sns.boxplot(x = "online_order", y = "rate", data = df)
```
Finding: Offline orders tend to have lower ratings compared to online orders.

### Online Order vs Type (Heatmap)
Code used:
```python
pivot_table = df.pivot_table(index = 'listed_in(type)', columns = 'online_order', aggfunc = "size", fill_value = 0)
sns.heatmap(pivot_table, annot = True, cmap = "YlGnBu", fmt = 'd')
plt.title("Heatmap")
plt.xlabel("Online Order")
plt.ylabel("Listed in (Type)")
plt.show()
```
Finding: Dining restaurants primarily accept offline orders, while cafes receive more online orders.

## Notes & Next Steps
- The notebook cells in `Analysis.ipynb` were not executed inside the environment; the report is assembled directly from the notebook source and in-notebook conclusions.
- To produce rendered plots in this markdown, run the notebook cells or execute the plotting code in a Python environment and save images to an `images/` folder, then reference them here.

---

Generated from `Analysis.ipynb`.
