Unit 3: 
Short Type Questions (2–3 sentence answers):

1. How do you add a new key-value pair to a dictionary in Python? Provide an example.
2. What is the difference between accessing a value in a dictionary and replacing it?
3. Write a Python statement to traverse a dictionary and print all keys.
4. What is the purpose of inheritance in Object-Oriented Programming?
5. Explain the concept of polymorphism with a simple example in Python
-----------------

ANSWERS:

1. To add a new key-value pair to a dictionary in Python, you simply assign a value to a new key:
   ```python
   my_dict = {'a': 1, 'b': 2}
   my_dict['c'] = 3
   ```
   Now, `my_dict` will be `{'a': 1, 'b': 2, 'c': 3}`.

2. Accessing a value in a dictionary retrieves the existing value associated with a key without modifying the dictionary itself. Replacing a value involves assigning a new value to an existing key, which updates the dictionary:
   ```python
   my_dict = {'a': 1, 'b': 2}
   value = my_dict['a']  # Accessing
   my_dict['b'] = 3      # Replacing
   ```

3. To traverse a dictionary and print all keys in Python:
   ```python
   my_dict = {'a': 1, 'b': 2, 'c': 3}
   for key in my_dict:
       print(key)
   ```

4. Inheritance in Object-Oriented Programming (OOP) allows one class (subclass or derived class) to inherit the properties and methods of another class (superclass or base class). It promotes code reuse, as subclasses can extend or modify the behavior of the superclass without rewriting existing code.

5. Polymorphism in Python refers to the ability of different objects to respond to the same method calls, thereby enabling different classes to be treated as instances of a common superclass. For example:
   ```python
   class Animal:
       def sound(self):
           pass

   class Dog(Animal):
       def sound(self):
           print("Woof")

   class Cat(Animal):
       def sound(self):
           print("Meow")

   def make_sound(animal):
       animal.sound()

   dog = Dog()
   cat = Cat()

   make_sound(dog)  # Outputs: Woof
   make_sound(cat)  # Outputs: Meow
   ```

