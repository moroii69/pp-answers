UNIT -- 04


Short Type Questions (2–3 sentence answers):
1.	How do you establish a connection to a MySQL database in Python? Provide the necessary code snippet.
2.	What is the difference between DML and DDL operations in a database? Give an example of each.
3.	Write a Python statement to execute a SQL INSERT operation using a database cursor.
4.	What is a database transaction? Why is it important?
5.	How can you handle database errors in Python? Mention one key method or class for error handling.

--------------------

### Unit 4: Short Type Questions

1. **How do you establish a connection to a MySQL database in Python? Provide the necessary code snippet.**  
   To establish a connection to a MySQL database in Python, you can use the `mysql.connector` module. Here's a code snippet:  
   ```python
   import mysql.connector
   conn = mysql.connector.connect(
       host="localhost",
       user="your_username",
       password="your_password",
       database="your_database"
   )
   ```

2. **What is the difference between DML and DDL operations in a database? Give an example of each.**  
   - **DML (Data Manipulation Language):** Deals with the manipulation of data, such as inserting, updating, or deleting records.  
     Example: `INSERT INTO students (name, age) VALUES ('John', 20);`  
   - **DDL (Data Definition Language):** Deals with the structure of the database, such as creating, altering, or deleting tables.  
     Example: `CREATE TABLE students (id INT, name VARCHAR(50), age INT);`

3. **Write a Python statement to execute a SQL INSERT operation using a database cursor.**  
   ```python
   cursor.execute("INSERT INTO students (name, age) VALUES (%s, %s)", ("John", 20))
   ```

4. **What is a database transaction? Why is it important?**  
   A database transaction is a sequence of operations performed as a single logical unit of work, ensuring that either all operations succeed or none of them are applied (atomicity). Transactions are important to maintain data integrity and consistency in case of errors or system failures.

5. **How can you handle database errors in Python? Mention one key method or class for error handling.**  
   You can handle database errors in Python using the `mysql.connector.Error` class. By wrapping database operations in a `try-except` block, you can catch and handle exceptions effectively.  
   Example:  
   ```python
   from mysql.connector import Error
   try:
       # Database operations
   except Error as e:
       print(f"Error: {e}")
   ```
