Long Type Questions (5–10 sentences with examples):
1.	Explain the steps to connect Python with a MySQL database. Write a program to create a database connection and a table.
2.	Write a Python program that performs basic CRUD (Create, Read, Update, Delete) operations on a MySQL database.
3.	Discuss DDL and DML operations with detailed examples in Python. Write a program to create a table (DDL) and insert data into it (DML).
4.	What is transaction handling in databases? Write a Python program to demonstrate a transaction with commit and rollback operations.
5.	Explain how database errors can be handled in Python. Write a program that catches and handles an error during a database operation.

------------------

### 1. Explain the steps to connect Python with a MySQL database. Write a program to create a database connection and a table.

To connect Python with a MySQL database, follow these steps:

1. **Install the MySQL Connector**: Use `pip install mysql-connector-python` to install the required library.
2. **Import the Connector**: Import the `mysql.connector` module in your Python script.
3. **Establish a Connection**: Use the `connect` method with appropriate parameters (host, user, password, and database).
4. **Create a Cursor Object**: Use the `cursor()` method to interact with the database.
5. **Execute SQL Queries**: Use the `execute()` method for SQL commands.
6. **Close the Connection**: Ensure to close the connection using `close()` after completing the operations.

Here’s a program to create a database connection and a table:

```python
import mysql.connector

try:
    # Establishing the connection
    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="yourpassword"
    )
    if conn.is_connected():
        print("Connected to MySQL Server")

    # Creating a database and a table
    cursor = conn.cursor()
    cursor.execute("CREATE DATABASE IF NOT EXISTS school")
    cursor.execute("USE school")
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS students (
            id INT AUTO_INCREMENT PRIMARY KEY,
            name VARCHAR(50),
            age INT
        )
    """)
    print("Database and table created successfully!")

except mysql.connector.Error as e:
    print(f"Error: {e}")

finally:
    if conn.is_connected():
        cursor.close()
        conn.close()
```

---

### 2. Write a Python program that performs basic CRUD (Create, Read, Update, Delete) operations on a MySQL database.

```python
import mysql.connector

try:
    # Establishing the connection
    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="yourpassword",
        database="school"
    )
    cursor = conn.cursor()

    # Create (Insert data)
    cursor.execute("INSERT INTO students (name, age) VALUES (%s, %s)", ("Alice", 20))
    conn.commit()
    print("Data inserted.")

    # Read (Retrieve data)
    cursor.execute("SELECT * FROM students")
    for row in cursor.fetchall():
        print(row)

    # Update (Modify data)
    cursor.execute("UPDATE students SET age = %s WHERE name = %s", (21, "Alice"))
    conn.commit()
    print("Data updated.")

    # Delete (Remove data)
    cursor.execute("DELETE FROM students WHERE name = %s", ("Alice",))
    conn.commit()
    print("Data deleted.")

except mysql.connector.Error as e:
    print(f"Error: {e}")

finally:
    if conn.is_connected():
        cursor.close()
        conn.close()
```

---

### 3. Discuss DDL and DML operations with detailed examples in Python.

**DDL (Data Definition Language):** Commands like `CREATE`, `ALTER`, and `DROP` used for defining database schema.
**DML (Data Manipulation Language):** Commands like `INSERT`, `UPDATE`, and `DELETE` used for manipulating data.

Program:

```python
import mysql.connector

try:
    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="yourpassword",
        database="school"
    )
    cursor = conn.cursor()

    # DDL: Creating a table
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS teachers (
            id INT AUTO_INCREMENT PRIMARY KEY,
            name VARCHAR(50),
            subject VARCHAR(50)
        )
    """)
    print("Table created.")

    # DML: Inserting data
    cursor.execute("INSERT INTO teachers (name, subject) VALUES (%s, %s)", ("Mr. Smith", "Math"))
    conn.commit()
    print("Data inserted.")

except mysql.connector.Error as e:
    print(f"Error: {e}")

finally:
    if conn.is_connected():
        cursor.close()
        conn.close()
```

---

### 4. What is transaction handling in databases? Write a Python program to demonstrate a transaction with commit and rollback operations.

**Transaction Handling:** Ensures all operations within a transaction block are completed successfully. If any operation fails, the transaction can be rolled back to maintain data integrity.

Program:

```python
import mysql.connector

try:
    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="yourpassword",
        database="school"
    )
    cursor = conn.cursor()

    # Starting a transaction
    conn.start_transaction()

    # Inserting data
    cursor.execute("INSERT INTO students (name, age) VALUES (%s, %s)", ("Bob", 22))
    cursor.execute("INSERT INTO students (name, age) VALUES (%s, %s)", ("Carol", 23))
    
    # Uncomment the following line to simulate an error
    # cursor.execute("INSERT INTO students (nonexistent_column) VALUES (%s)", ("Error",))

    conn.commit()  # Commit the transaction if no errors
    print("Transaction committed.")

except mysql.connector.Error as e:
    conn.rollback()  # Rollback the transaction on error
    print(f"Transaction rolled back. Error: {e}")

finally:
    if conn.is_connected():
        cursor.close()
        conn.close()
```

---

### 5. Explain how database errors can be handled in Python. Write a program that catches and handles an error during a database operation.

Database errors can occur due to connection issues, invalid queries, or constraint violations. Use `try-except` blocks to catch and handle these errors.

Program:

```python
import mysql.connector

try:
    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="yourpassword",
        database="school"
    )
    cursor = conn.cursor()

    # Attempting to insert into a non-existent table
    cursor.execute("INSERT INTO nonexistent_table (name) VALUES (%s)", ("John",))
    conn.commit()

except mysql.connector.Error as e:
    print(f"Database error occurred: {e}")

finally:
    if conn.is_connected():
        cursor.close()
        conn.close()
```
