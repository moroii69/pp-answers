Long Type Questions (5–10 sentences with examples):
1.	Discuss the basic operations on dictionaries in Python, including adding, removing keys, and accessing values. Provide a program to demonstrate these operations.
2.	Write a Python program that demonstrates set operations such as union, intersection, difference, and checking membership.
3.	Explain the concept of classes and objects in Python. Write a program to define a class with attributes and methods, and create multiple objects from it.
4.	Discuss the concept of inheritance in Python with examples. Show how child classes can override methods of the parent class.
5.	What is exception handling in Python? Explain with an example that demonstrates the use of try, except, and finally.

-------------------

### 1. Discuss the basic operations on dictionaries in Python, including adding, removing keys, and accessing values. Provide a program to demonstrate these operations.

**Answer:**
Dictionaries in Python are used to store data in key-value pairs. Common operations include:
- **Adding items:** Adding a key-value pair is done by assigning a value to a key (`dict[key] = value`).
- **Removing items:** Use the `pop()` method or the `del` statement to remove items by their keys.
- **Accessing values:** Use the key inside square brackets (`dict[key]`) or the `get()` method to retrieve values.

**Program:**
```python
# Creating a dictionary
student = {"name": "John", "age": 21, "grade": "A"}

# Adding a key-value pair
student["major"] = "Computer Science"

# Accessing a value
print("Student's name:", student["name"])

# Removing a key-value pair
student.pop("age")

# Iterating through the dictionary
print("Updated dictionary:")
for key, value in student.items():
    print(key, ":", value)
```

---

### 2. Write a Python program that demonstrates set operations such as union, intersection, difference, and checking membership.

**Answer:**
Sets in Python are unordered collections of unique elements. Operations include:
- **Union:** Combines all unique elements from two sets (`set1 | set2` or `set1.union(set2)`).
- **Intersection:** Retrieves common elements (`set1 & set2` or `set1.intersection(set2)`).
- **Difference:** Finds elements in one set but not in the other (`set1 - set2` or `set1.difference(set2)`).
- **Membership check:** Use the `in` keyword.

**Program:**
```python
# Defining two sets
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

# Union
print("Union:", set_a | set_b)

# Intersection
print("Intersection:", set_a & set_b)

# Difference
print("Difference (set_a - set_b):", set_a - set_b)

# Membership check
print("Is 2 in set_a?", 2 in set_a)
```

---

### 3. Explain the concept of classes and objects in Python. Write a program to define a class with attributes and methods, and create multiple objects from it.

**Answer:**
In Python, a **class** is a blueprint for creating objects. It defines attributes (variables) and methods (functions) that the objects of the class will have. An **object** is an instance of a class. Objects can have different values for their attributes but share the class's methods.

**Program:**
```python
# Defining a class
class Car:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year

    def display_info(self):
        print(f"{self.year} {self.brand} {self.model}")

# Creating objects
car1 = Car("Toyota", "Corolla", 2020)
car2 = Car("Honda", "Civic", 2019)

# Accessing methods
car1.display_info()
car2.display_info()
```

---

### 4. Discuss the concept of inheritance in Python with examples. Show how child classes can override methods of the parent class.

**Answer:**
Inheritance in Python allows a class (child) to inherit attributes and methods from another class (parent). It promotes code reuse and hierarchy. Child classes can override parent class methods by defining them with the same name.

**Program:**
```python
# Parent class
class Animal:
    def sound(self):
        print("This animal makes a sound.")

# Child class
class Dog(Animal):
    def sound(self):  # Overriding the parent method
        print("The dog barks.")

# Another child class
class Cat(Animal):
    def sound(self):  # Overriding the parent method
        print("The cat meows.")

# Using the classes
animal = Animal()
dog = Dog()
cat = Cat()

animal.sound()
dog.sound()
cat.sound()
```

---

### 5. What is exception handling in Python? Explain with an example that demonstrates the use of try, except, and finally.

**Answer:**
Exception handling in Python is used to manage errors that occur during program execution, allowing the program to continue running. The `try` block contains the code that may raise an exception. The `except` block handles the exception. The `finally` block contains code that runs regardless of whether an exception occurred.

**Program:**
```python
try:
    # Code that might raise an exception
    num = int(input("Enter a number: "))
    result = 100 / num
    print("Result:", result)
except ValueError:
    # Handling a specific exception
    print("Invalid input. Please enter a valid number.")
except ZeroDivisionError:
    # Handling another specific exception
    print("Cannot divide by zero.")
finally:
    # Code that runs no matter what
    print("Execution complete.")
```
