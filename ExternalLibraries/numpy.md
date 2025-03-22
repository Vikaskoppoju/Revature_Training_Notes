
### **What is NumPy? 🤔**  
NumPy (**Numerical Python**) is a powerful library for **fast numerical computing** in Python. It helps in **handling large datasets**, **performing mathematical operations**, and **working with multi-dimensional arrays** like a pro! 😎🔥  

📌 **Why Use NumPy?**  
✅ **Faster** than Python lists  
✅ **Uses less memory**  
✅ **Supports matrix operations**  
✅ **Comes with tons of built-in functions**  

---

## **🛠️ 1. Installing NumPy**  
You can install NumPy using **pip**:
```bash
pip install numpy
```
Or inside a **Jupyter Notebook**:
```python
!pip install numpy
```
Now, let's dive into **NumPy!** ✨🐍  

---

## **📌 2. Creating NumPy Arrays**  
Unlike Python lists, NumPy arrays are **faster and more efficient**! 🚀  

### **🔹 Creating a Simple Array**
```python
import numpy as np

# 1D Array
arr1 = np.array([10, 20, 30, 40, 50])
print(arr1)

# 2D Array (Matrix)
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
print(arr2)
```
💡 **NumPy arrays are homogeneous** (all elements must have the same data type).

---

## **📊 3. Understanding Array Properties**
```python
print("Shape:", arr2.shape)  # (2,3) → 2 rows, 3 columns
print("Dimensions:", arr2.ndim)  # Number of dimensions
print("Size:", arr2.size)  # Total elements
print("Data type:", arr2.dtype)  # int32 or float64
```
**Example Output:**
```
Shape: (2, 3)
Dimensions: 2
Size: 6
Data type: int32
```

---

## **🎨 4. Creating Special Arrays**
### **🔹 All Zeros or Ones**
```python
zeros = np.zeros((3, 4))  # 3x4 matrix of zeros
ones = np.ones((2, 3))  # 2x3 matrix of ones
```

### **🔹 Evenly Spaced Numbers**
```python
arr3 = np.arange(1, 10, 2)  # [1, 3, 5, 7, 9]
arr4 = np.linspace(0, 5, 10)  # 10 values between 0 and 5
```

### **🔹 Random Numbers 🎲**
```python
rand_arr = np.random.rand(3, 3)  # 3x3 matrix with values [0,1)
rand_ints = np.random.randint(1, 100, (2, 2))  # 2x2 random integers (1-99)
```

---

## **🎯 5. Indexing & Slicing in NumPy**
NumPy arrays work like Python lists, but better! 🔥

```python
arr = np.array([10, 20, 30, 40, 50])

print(arr[0])  # First element (10)
print(arr[-1])  # Last element (50)
print(arr[1:4])  # Elements from index 1 to 3 → [20, 30, 40]
print(arr[::2])  # Every second element → [10, 30, 50]
```

### **🔹 Indexing in 2D Arrays**
```python
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print(matrix[1, 2])  # Row 1, Column 2 → 6
print(matrix[:, 1])  # All rows, Column 1 → [2, 5, 8]
print(matrix[0:2, 1:3])  # Sub-matrix from rows 0-1 and cols 1-2
```

---

## **⚡ 6. Performing Mathematical Operations**
NumPy makes mathematical operations **lightning fast!** ⚡

```python
arr = np.array([1, 2, 3, 4])

print(arr + 10)  # Add 10 to each element
print(arr * 2)   # Multiply each element by 2
print(arr ** 2)  # Square each element
print(np.sqrt(arr))  # Square root of each element
```

### **🔹 Matrix Operations**
```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

print(A + B)  # Element-wise addition
print(A * B)  # Element-wise multiplication
print(np.dot(A, B))  # Matrix multiplication
```

---

## **📈 7. Statistical & Aggregate Functions**
```python
arr = np.array([10, 20, 30, 40, 50])

print("Sum:", np.sum(arr))  # 150
print("Mean:", np.mean(arr))  # 30
print("Median:", np.median(arr))  # 30
print("Standard Deviation:", np.std(arr))  # 14.14
```

### **🔹 Column-wise & Row-wise Operations**
```python
matrix = np.array([[1, 2, 3], [4, 5, 6]])

print(np.sum(matrix, axis=0))  # Sum along columns
print(np.sum(matrix, axis=1))  # Sum along rows
```

---

## **🔄 8. Reshaping & Transposing Arrays**
```python
arr = np.arange(1, 10)

reshaped = arr.reshape(3, 3)  # Reshape to 3x3
transposed = reshaped.T  # Transpose (swap rows & columns)
```

---

## **🔀 9. Stacking & Splitting Arrays**
### **🔹 Stacking**
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

print(np.vstack((arr1, arr2)))  # Vertical stack
print(np.hstack((arr1, arr2)))  # Horizontal stack
```

### **🔹 Splitting**
```python
arr = np.array([1, 2, 3, 4, 5, 6])

split_arr = np.split(arr, 2)  # Split into 2 equal parts
```

---

## **🎭 10. Boolean Masking & Filtering**
```python
arr = np.array([10, 20, 30, 40, 50])

mask = arr > 25  # Boolean mask for values > 25
print(arr[mask])  # [30, 40, 50]
```

---

## **🛠️ 11. Handling NaN (Missing Values)**
```python
arr = np.array([10, np.nan, 20, np.nan, 30])

print(np.isnan(arr))  # Identify NaN values
print(np.nanmean(arr))  # Mean ignoring NaN values
```

---

## **🔥 Recap of Key NumPy Functions**
| Feature | Function |
|---------|----------|
| Create an array | `np.array([1,2,3])` |
| Create zeros/ones | `np.zeros((2,3))`, `np.ones((3,3))` |
| Generate sequences | `np.arange(1,10,2)`, `np.linspace(0,5,10)` |
| Random numbers | `np.random.rand(3,3)`, `np.random.randint(1,100,(2,2))` |
| Math operations | `arr + 10`, `arr * 2`, `np.sqrt(arr)` |
| Aggregate functions | `np.sum(arr)`, `np.mean(arr)`, `np.std(arr)` |
| Reshape arrays | `arr.reshape(3,3)`, `arr.T` |
| Filtering | `arr[arr > 25]` |

---
