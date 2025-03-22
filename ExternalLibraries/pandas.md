
---

## **📌 What is Pandas?**  

Pandas is an **open-source data analysis library** built on top of **NumPy**. It provides powerful tools for **data manipulation, transformation, and analysis**.

### **💡 Why Use Pandas?**  
✅ Simplifies **data handling (loading, transforming, filtering, and analyzing)**  
✅ Works with **structured data (CSV, Excel, SQL, JSON, etc.)**  
✅ Provides **powerful data cleaning, grouping, and aggregation tools**  
✅ Used in **data science, finance, web scraping, machine learning, and research**  

### **Installation & Setup**  
```python
pip install pandas
```
```python
import pandas as pd  # Standard alias
```

---

# **🔹 1. Understanding Pandas Series (One-Dimensional Data) 📊**  

A **Series** is a **one-dimensional labeled array** that holds **any data type** (integers, floats, strings, etc.). Think of it as a **single column of a spreadsheet**.  

### **Creating a Pandas Series**
```python
# Creating a Series from a list
s = pd.Series([10, 20, 30, 40, 50])
print(s)
```
**Output:**
```
0    10
1    20
2    30
3    40
4    50
dtype: int64
```

### **Specifying Custom Index Labels**
```python
s = pd.Series([100, 200, 300], index=['a', 'b', 'c'])
print(s)
```
**Output:**
```
a    100
b    200
c    300
dtype: int64
```

### **Accessing Elements in a Series**
```python
print(s['a'])  # Access using index label
print(s[0])  # Access using integer index
```

### **Common Series Methods**
```python
print(s.mean())   # Average value
print(s.sum())    # Total sum
print(s.max())    # Maximum value
print(s.min())    # Minimum value
print(s.describe())  # Summary statistics
```

---

# **🔹 2. Understanding Pandas DataFrame (Two-Dimensional Data) 🏗**  

A **DataFrame** is a **2D labeled table** that consists of **rows and columns**. It's like an **Excel sheet or SQL table**.

### **Creating a DataFrame from a Dictionary**
```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 30, 35, 40],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston']
}
df = pd.DataFrame(data)
print(df)
```
**Output:**
```
     Name  Age         City
0   Alice   25    New York
1     Bob   30  Los Angeles
2  Charlie   35     Chicago
3   David   40     Houston
```

### **Creating a DataFrame from a List of Lists**
```python
data = [['Alice', 25, 'New York'],
        ['Bob', 30, 'Los Angeles'],
        ['Charlie', 35, 'Chicago']]
df = pd.DataFrame(data, columns=['Name', 'Age', 'City'])
print(df)
```

### **Checking DataFrame Information**
```python
print(df.info())  # Structure of DataFrame
print(df.shape)  # (rows, columns)
print(df.columns)  # Column names
print(df.dtypes)  # Data types of each column
```

---

# **🔹 3. Reading & Writing CSV/Excel Files 📄**  

### **Reading a CSV File**
```python
df = pd.read_csv("data.csv")
print(df.head())  # Show first 5 rows
```

### **Reading an Excel File**
```python
df = pd.read_excel("data.xlsx", sheet_name="Sheet1")
```

### **Writing to a CSV File**
```python
df.to_csv("output.csv", index=False)
```

### **Writing to an Excel File**
```python
df.to_excel("output.xlsx", index=False)
```

---

# **🔹 4. Exploring Data 🕵️**  

### **Basic Summary Statistics**
```python
print(df.describe())  # Get summary statistics
print(df['Age'].mean())  # Average age
print(df['Age'].median())  # Median age
print(df['Age'].std())  # Standard deviation
```

### **Checking for Missing Values**
```python
print(df.isnull().sum())  # Count missing values per column
```

---

# **🔹 5. Selecting & Filtering Data 🎯**  

### **Selecting a Single Column**
```python
print(df['Age'])
```

### **Selecting Multiple Columns**
```python
print(df[['Name', 'Age']])
```

### **Filtering Rows**
```python
print(df[df['Age'] > 30])  # Get rows where Age > 30
```

### **Filtering with Multiple Conditions**
```python
print(df[(df['Age'] > 30) & (df['City'] == 'New York')])
```

---

# **🔹 6. Sorting & Grouping Data 📊**  

### **Sorting a DataFrame**
```python
print(df.sort_values(by='Age'))  # Ascending order
print(df.sort_values(by='Age', ascending=False))  # Descending order
```

### **Grouping Data**
```python
print(df.groupby('City')['Age'].mean())  # Average Age per City
```

---

# **🔹 7. Handling Missing Values 🚨**  

### **Dropping Rows with Missing Values**
```python
df_cleaned = df.dropna()
```

### **Filling Missing Values**
```python
df['Age'].fillna(df['Age'].mean(), inplace=True)
```

---

# **🔹 8. Applying Functions to Data 🛠**  

### **Applying a Lambda Function**
```python
df['Age_squared'] = df['Age'].apply(lambda x: x**2)
```

---

# **🔹 9. Merging & Joining DataFrames 🔗**  

### **Merging Two DataFrames**
```python
df1 = pd.DataFrame({'ID': [1, 2, 3], 'Name': ['Alice', 'Bob', 'Charlie']})
df2 = pd.DataFrame({'ID': [1, 2, 4], 'Score': [85, 90, 88]})

merged_df = pd.merge(df1, df2, on='ID', how='inner')  # Inner Join
print(merged_df)
```

---

# **🔹 10. Pivot Tables & Crosstabs 📊**  

### **Creating a Pivot Table**
```python
pivot = df.pivot_table(values='Age', index='City', aggfunc='mean')
print(pivot)
```

### **Creating a Crosstab**
```python
crosstab = pd.crosstab(df['City'], df['Age'])
print(crosstab)
```

---
