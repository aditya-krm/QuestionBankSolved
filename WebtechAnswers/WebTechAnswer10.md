# Question:

10. Consider the following and write the code to establish a connection with a MySql database. Database Name: db_student, Database user’s name: student, Database password: cse

# Answer:

## Connecting to MySQL Database with Python

Here's how to establish a connection to a MySQL database using Python:

```python
import mysql.connector

# Database connection details
db_config = {
    'host': 'localhost',  # Assuming the database is on the same machine
    'database': 'db_student',
    'user': 'student',
    'password': 'cse'
}

# Attempt to connect
try:
    connection = mysql.connector.connect(**db_config)
    print("Connection established successfully!")
except mysql.connector.Error as err:
    print(f"Error connecting to MySQL: {err}")

# (Optional) Example of executing a simple query
cursor = connection.cursor()
cursor.execute("SELECT * FROM students")  # Replace 'students' with your actual table name
result = cursor.fetchall()
print(result)

# Remember to close the connection
connection.close()
```

**Explanation:**

1. **Import the library:** We import the `mysql.connector` library to work with MySQL databases.
2. **Database configuration:** We define a dictionary `db_config` containing the database connection details like host, database name, username, and password.
3. **Connection attempt:** We use `mysql.connector.connect()` with the configuration to establish a connection. The `try-except` block handles potential errors during connection.
4. **(Optional) Query execution:** This demonstrates how to execute a simple query to fetch all data from a table named "students". Remember to replace this with your actual table name.
5. **Closing the connection:** It's crucial to close the connection using `connection.close()` when you're finished with your database operations.

**Important notes:**

* Make sure you have the `mysql-connector-python` library installed. You can install it using pip: `pip install mysql-connector-python`
* This code assumes the database is running on the same machine (localhost). If it's on a different server, replace 'localhost' with the server's IP address or hostname.
* Adapt the query in the example to match your specific needs.

**Security considerations:**

* Avoid hardcoding your password directly in the code. Consider using environment variables or a secrets management solution to store sensitive information securely. 
* Be cautious when granting database access. Only grant the necessary privileges to the user. 
