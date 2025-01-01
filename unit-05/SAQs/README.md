UNIT -- 05
Short Type Questions (2–3 sentence answers):
1.	What is NumPy, and why is it important for data analysis in Python?
2.	How do you create a NumPy array from a Python list? Provide an example.
3.	What is a Pandas Series? How is it different from a NumPy array?
4.	What is the purpose of the drop() method in Pandas? Write an example.
5.	Explain what happens when missing data is encountered in a Pandas DataFrame. How can it be handled?
6.	What happens when you add a scalar to an array?
7.	How do you access the second element of a 1D array?
________________________________________



1. **What is NumPy, and why is it important for data analysis in Python?**  
   NumPy is a Python library used for numerical computations, offering efficient handling of large arrays and matrices along with a collection of mathematical functions. It is essential for data analysis due to its speed, support for multidimensional data, and integration with other data science libraries like Pandas and SciPy.

2. **How do you create a NumPy array from a Python list? Provide an example.**  
   You can create a NumPy array from a Python list using the `numpy.array()` function.  
   **Example:**  
   ```python
   import numpy as np
   python_list = [1, 2, 3, 4]
   numpy_array = np.array(python_list)
   print(numpy_array)
   ```

3. **What is a Pandas Series? How is it different from a NumPy array?**  
   A Pandas Series is a one-dimensional labeled array capable of holding any data type. Unlike NumPy arrays, a Series has labeled indices, making it more flexible for handling structured data.

4. **What is the purpose of the drop() method in Pandas? Write an example.**  
   The `drop()` method is used to remove rows or columns from a DataFrame.  
   **Example:**  
   ```python
   import pandas as pd
   df = pd.DataFrame({'A': [1, 2], 'B': [3, 4]})
   df = df.drop('A', axis=1)  # Drops column 'A'
   print(df)
   ```

5. **Explain what happens when missing data is encountered in a Pandas DataFrame. How can it be handled?**  
   Missing data in a Pandas DataFrame is represented as `NaN`. It can be handled by removing rows/columns with missing data using `dropna()` or filling missing values with `fillna()`.

6. **What happens when you add a scalar to an array?**  
   Adding a scalar to an array in NumPy performs element-wise addition, where the scalar is added to each element of the array.

7. **How do you access the second element of a 1D array?**  
   Use indexing to access the second element by referring to its index, which is `1` (0-based indexing).  
   **Example:**  
   ```python
   array = np.array([10, 20, 30])
   second_element = array[1]
   print(second_element)
   ```
