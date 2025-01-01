UNIT -- 05


Long Type Questions (5–10 sentences with examples):
1.	Discuss the core functionalities of NumPy. Write a Python program to demonstrate array creation, indexing, and transposition.
2.	Explain Universal Array Functions in NumPy with examples. Demonstrate at least two functions, such as np.sqrt and np.mean.
3.	What is a Pandas DataFrame? Write a program to create a DataFrame, reindex it, and drop an entry.
4.	Explain the process of data alignment in Pandas with an example program. Include how Pandas aligns indices during operations.
5.	What is the significance of handling missing data in Pandas? Write a program to detect, fill, and drop missing values in a DataFrame.
6.	Explain the concept of transposing an array in NumPy. How do you perform array transposition for 1D, 2D, and multi-dimensional arrays? Provide examples.
7.	Describe Array Processing in NumPy. How do you perform arithmetic operations, broadcasting, and aggregate functions (like sum, mean, max) on arrays? Provide examples.
8.	Explain the concept of a Series in Pandas. How is a Series created, and what are its key attributes and methods? Provide examples. Discuss the differences between a Series and a list or NumPy array.?
9.	What is the purpose of the reindex() function in Pandas? How does it work, and why is it useful? Explain with a suitable example.
10.	What is Index Hierarchy in Pandas? How can you create and manipulate multi-level indices? Provide examples using hierarchical indexing in DataFrames and Series.
11.	What are the different summary statistics functions in Pandas? How are these used to summarize data in a DataFrame? Explain with examples.
12.	Explain data alignment in Pandas. How does Pandas align data while performing operations on Series or DataFrames? Use examples to illustrate this.





---

### 1. Discuss the core functionalities of NumPy. Write a Python program to demonstrate array creation, indexing, and transposition.

NumPy is a powerful library in Python for numerical computing. It provides support for multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays. Core functionalities include efficient array handling, broadcasting for arithmetic operations, integration with C/C++, and support for linear algebra, Fourier transforms, and random number generation. NumPy arrays, unlike Python lists, are more memory-efficient and faster due to their homogeneous nature.

**Example Python Program:**
```python
import numpy as np

# Array creation
array = np.array([[1, 2, 3], [4, 5, 6]])
print("Original Array:\n", array)

# Indexing
print("Element at row 0, column 1:", array[0, 1])

# Transposition
transposed_array = array.T
print("Transposed Array:\n", transposed_array)
```

---

### 2. Explain Universal Array Functions in NumPy with examples. Demonstrate at least two functions, such as `np.sqrt` and `np.mean`.

Universal Array Functions (UFuncs) in NumPy are operations that are applied element-wise to arrays. They are highly optimized for performance. UFuncs include mathematical operations like addition, subtraction, square root, trigonometric functions, etc.

**Examples:**
```python
import numpy as np

# Create an array
array = np.array([1, 4, 9, 16])

# Square root
sqrt_array = np.sqrt(array)
print("Square Root:\n", sqrt_array)

# Mean
mean_value = np.mean(array)
print("Mean Value:", mean_value)
```

---

### 3. What is a Pandas DataFrame? Write a program to create a DataFrame, reindex it, and drop an entry.

A Pandas DataFrame is a two-dimensional, mutable data structure with labeled axes (rows and columns). It is similar to a spreadsheet or SQL table. DataFrames are useful for data manipulation, analysis, and visualization tasks.

**Example:**
```python
import pandas as pd

# Create a DataFrame
data = {'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]}
df = pd.DataFrame(data)
print("Original DataFrame:\n", df)

# Reindex
df_reindexed = df.reindex([2, 1, 0])
print("\nReindexed DataFrame:\n", df_reindexed)

# Drop an entry
df_dropped = df.drop('B', axis=1)
print("\nDataFrame after dropping column 'B':\n", df_dropped)
```

---

### 4. Explain the process of data alignment in Pandas with an example program.

Data alignment in Pandas ensures that operations between Series or DataFrames are performed based on matching indices. When performing operations, Pandas aligns data on the axes. Missing values are filled with `NaN`.

**Example:**
```python
import pandas as pd

# Create two Series
s1 = pd.Series([1, 2, 3], index=['a', 'b', 'c'])
s2 = pd.Series([4, 5, 6], index=['b', 'c', 'd'])

# Add the Series
result = s1 + s2
print("Aligned Series:\n", result)
```

---

### 5. What is the significance of handling missing data in Pandas? Write a program to detect, fill, and drop missing values in a DataFrame.

Handling missing data is crucial for ensuring the quality and reliability of data analysis. Missing values can lead to incorrect results or errors in computations. Pandas provides methods to detect, fill, and drop missing values.

**Example:**
```python
import pandas as pd
import numpy as np

# Create a DataFrame with missing values
data = {'A': [1, 2, np.nan], 'B': [4, np.nan, 6], 'C': [7, 8, 9]}
df = pd.DataFrame(data)
print("Original DataFrame:\n", df)

# Detect missing values
print("\nMissing Values:\n", df.isnull())

# Fill missing values
df_filled = df.fillna(0)
print("\nDataFrame after filling missing values:\n", df_filled)

# Drop missing values
df_dropped = df.dropna()
print("\nDataFrame after dropping missing values:\n", df_dropped)
```

---

### 6. Explain the concept of transposing an array in NumPy. How do you perform array transposition for 1D, 2D, and multi-dimensional arrays? Provide examples.

Transposing an array involves flipping it over its diagonal. For a 2D array, rows become columns and vice versa. In NumPy, this is achieved using `.T`.

**Examples:**
```python
import numpy as np

# 1D Array (No change on transposition)
array_1d = np.array([1, 2, 3])
print("1D Array Transposed:\n", array_1d.T)

# 2D Array
array_2d = np.array([[1, 2], [3, 4]])
print("\n2D Array Transposed:\n", array_2d.T)

# Multi-dimensional Array
array_3d = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
print("\n3D Array Transposed:\n", array_3d.transpose(1, 0, 2))
```

---

### 7. Describe Array Processing in NumPy. How do you perform arithmetic operations, broadcasting, and aggregate functions (like sum, mean, max) on arrays? Provide examples.

Array processing in NumPy involves performing mathematical and logical operations efficiently. Arithmetic operations can be applied directly to arrays. Broadcasting allows operations on arrays of different shapes by extending the smaller array. Aggregate functions compute summaries over axes.

**Examples:**
```python
import numpy as np

# Arithmetic Operations
array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])
print("Addition:\n", array1 + array2)

# Broadcasting
array3 = np.array([[1, 2, 3], [4, 5, 6]])
array4 = np.array([1, 2, 3])
print("\nBroadcasting:\n", array3 + array4)

# Aggregate Functions
print("\nSum:", np.sum(array3))
print("Mean:", np.mean(array3))
print("Max:", np.max(array3))
```

---

### 8. Explain the concept of a Series in Pandas. How is a Series created, and what are its key attributes and methods? Provide examples. Discuss the differences between a Series and a list or NumPy array.

A Pandas Series is a one-dimensional labeled array capable of holding any data type. It has indices for data elements, allowing for easy alignment and manipulation. Unlike lists or NumPy arrays, Series have both values and labels (index).

**Example:**
```python
import pandas as pd

# Create a Series
series = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
print("Series:\n", series)

# Key Attributes and Methods
print("\nValues:", series.values)
print("Index:", series.index)
print("Sum:", series.sum())
```

**Differences:**
- **Labels**: Series have indices; lists and NumPy arrays do not.
- **Operations**: Series align data by labels during operations.

---



### 9. What is the purpose of the `reindex()` function in Pandas? How does it work, and why is it useful? Explain with a suitable example.

The `reindex()` function in Pandas is used to conform a Series or DataFrame to a new index. It enables you to rearrange or add missing indices, with missing data filled as `NaN` by default. This is particularly useful for aligning data, filling gaps, or reorganizing datasets.

**Key Points:**
- Changes the index to match a given list.
- Allows for forward/backward filling of missing indices using parameters like `method='ffill'` or `method='bfill'`.
- Can reorder rows or columns.

**Example:**
```python
import pandas as pd

# Create a DataFrame
data = {'A': [1, 2, 3], 'B': [4, 5, 6]}
df = pd.DataFrame(data, index=['a', 'b', 'c'])
print("Original DataFrame:\n", df)

# Reindex with a new index
new_index = ['b', 'c', 'd', 'e']
df_reindexed = df.reindex(new_index)
print("\nReindexed DataFrame:\n", df_reindexed)

# Filling missing values
df_filled = df.reindex(new_index, fill_value=0)
print("\nReindexed DataFrame with Filled Values:\n", df_filled)
```

---

### 10. What is Index Hierarchy in Pandas? How can you create and manipulate multi-level indices? Provide examples using hierarchical indexing in DataFrames and Series.

Index Hierarchy in Pandas, also known as MultiIndex, allows for multiple levels of indexing on axes. This is useful for working with datasets that have multi-dimensional relationships, enabling complex data organization and access.

**Key Features:**
- Enables multi-dimensional data representation.
- Allows slicing and subsetting data based on levels.

**Creating and Manipulating MultiIndex:**
```python
import pandas as pd

# Create a MultiIndex DataFrame
arrays = [['A', 'A', 'B', 'B'], [1, 2, 1, 2]]
index = pd.MultiIndex.from_tuples(list(zip(*arrays)), names=['Group', 'Number'])
data = [[10, 20], [30, 40], [50, 60], [70, 80]]
df = pd.DataFrame(data, index=index, columns=['X', 'Y'])
print("DataFrame with MultiIndex:\n", df)

# Access data by levels
print("\nData for Group 'A':\n", df.loc['A'])

# Resetting the index
df_reset = df.reset_index()
print("\nDataFrame after Resetting Index:\n", df_reset)
```

---

### 11. What are the different summary statistics functions in Pandas? How are these used to summarize data in a DataFrame? Explain with examples.

Pandas provides several summary statistics functions to compute metrics like mean, sum, median, variance, and more. These functions can be applied along rows or columns using the `axis` parameter. They help in understanding data distributions and patterns.

**Common Functions:**
- `mean()`: Average value.
- `sum()`: Total sum.
- `median()`: Middle value.
- `std()`: Standard deviation.
- `describe()`: Summary statistics for all numerical columns.

**Example:**
```python
import pandas as pd

# Create a DataFrame
data = {'A': [10, 20, 30], 'B': [15, 25, 35], 'C': [5, 10, 15]}
df = pd.DataFrame(data)
print("Original DataFrame:\n", df)

# Apply summary functions
print("\nMean of Each Column:\n", df.mean())
print("\nSum of Each Row:\n", df.sum(axis=1))
print("\nDescribe:\n", df.describe())
```

---

### 12. Explain data alignment in Pandas. How does Pandas align data while performing operations on Series or DataFrames? Use examples to illustrate this.

Data alignment in Pandas ensures that operations between Series or DataFrames are performed based on matching indices. If an index is missing in one of the objects, the result will contain `NaN` for that position. This behavior simplifies handling datasets with differing indices.

**Key Features:**
- Operates on index labels rather than positions.
- Ensures alignment for operations like addition or subtraction.
- Handles missing data with `NaN`.

**Example:**
```python
import pandas as pd

# Create two Series with different indices
s1 = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
s2 = pd.Series([40, 50, 60], index=['b', 'c', 'd'])

# Perform addition
result = s1 + s2
print("Series 1:\n", s1)
print("\nSeries 2:\n", s2)
print("\nResult of Addition with Data Alignment:\n", result)

# DataFrame alignment
df1 = pd.DataFrame({'A': [1, 2], 'B': [3, 4]}, index=['x', 'y'])
df2 = pd.DataFrame({'B': [5, 6], 'C': [7, 8]}, index=['y', 'z'])
df_result = df1 + df2
print("\nDataFrame Alignment Result:\n", df_result)
```

---

