# SQL Theory and Commands 

## 1. Introduction to SQL
- **Definition**: SQL (Structured Query Language) is a standard programming language used to manage and manipulate relational databases.
- **Purpose**: SQL is used for querying, updating, and managing data in a database. It allows users to perform various operations on the data stored in relational databases.

## 2. Importance of SQL
- **Data Manipulation**: SQL provides powerful commands to insert, update, delete, and retrieve data.
- **Data Definition**: SQL allows users to define the structure of the database, including tables, fields, and relationships.
- **Data Control**: SQL includes commands for managing access to data and ensuring data integrity.

## 3. SQL Commands
SQL commands can be categorized into several types based on their functionality:

### 3.1 Data Definition Language (DDL)
- **Definition**: DDL commands are used to define and manage all database objects.
- **Common DDL Commands**:
  - **CREATE**: Used to create a new database or table.
    - **Example**: 
      ```sql
      CREATE TABLE Students (
          StudentID INT PRIMARY KEY,
          StudentName VARCHAR(50),
          DateOfBirth DATE
      );
      ```
  - **ALTER**: Used to modify an existing database object.
    - **Example**: 
      ```sql
      ALTER TABLE Students ADD Email VARCHAR(100);
      ```
  - **DROP**: Used to delete a database or table.
    - **Example**: 
      ```sql
      DROP TABLE Students;
      ```

### 3.2 Data Manipulation Language (DML)
- **Definition**: DML commands are used to manipulate data within existing database objects.
- **Common DML Commands**:
  - **INSERT**: Used to add new records to a table.
    - **Example**: 
      ```sql
      INSERT INTO Students (StudentID, StudentName, DateOfBirth) 
      VALUES (1, 'Alice', '2003-05-15');
      ```
  - **UPDATE**: Used to modify existing records in a table.
    - **Example**: 
      ```sql
      UPDATE Students 
      SET StudentName = 'Alice Smith' 
      WHERE StudentID = 1;
      ```
  - **DELETE**: Used to remove records from a table.
    - **Example**: 
      ```sql
      DELETE FROM Students 
      WHERE StudentID = 1;
      ```

### 3.3 Data Query Language (DQL)
- **Definition**: DQL commands are used to query and retrieve data from the database.
- **Common DQL Command**:
  - **SELECT**: Used to retrieve data from one or more tables.
    - **Example**: 
      ```sql
      SELECT * FROM Students;
      ```
    - **Example with Conditions**: 
      ```sql
      SELECT StudentName FROM Students 
      WHERE DateOfBirth < '2003-01-01';
      ```

### 3.4 Data Control Language (DCL)
- **Definition**: DCL commands are used to control access to data in the database.
- **Common DCL Commands**:
  - **GRANT**: Used to provide users with access privileges to the database.
    - **Example**: 
      ```sql
      GRANT SELECT ON Students TO User1;
      ```
  - **REVOKE**: Used to remove access privileges from users.
    - **Example**: 
      ```sql
      REVOKE SELECT ON Students FROM User1;
      ```

## 4. SQL Syntax
- **General Syntax**: SQL commands are not case-sensitive, but it is a common practice to write keywords in uppercase for better readability.
- **Semicolon**: Each SQL statement should end with a semicolon (`;`).

## 5. SQL Functions
SQL provides various built-in functions to perform operations on data.

### 5.1 Aggregate Functions
- **Definition**: Functions that perform a calculation on a set of values and return a single value.
- **Common Aggregate Functions**:
  - **COUNT()**: Returns the number of rows that match a specified criterion.
    - **Example**: 
      ```sql
      SELECT COUNT(*) FROM Students;
      ```
  - **SUM()**: Returns the total sum of a numeric column.
    - **Example**: 
      ```sql
      SELECT SUM(Score) FROM ExamResults;
      ```
  - **AVG()**: Returns the average value of a numeric column.
    - **Example**: 
      ```sql
      SELECT AVG(Score) FROM ExamResults;
      ```
  - **MAX()**: Returns the maximum value in a set.
    - **Example**: 
      ```sql
      SELECT MAX(Score) FROM ExamResults;
      ```
  - **MIN()**: Returns the minimum value in a set.
    - **Example**: 
      ```sql
      SELECT MIN(Score) FROM ExamResults;
      ```

### 5.2 String Functions
- **Definition**: Functions that perform operations on string data types.
- **Common String Functions**:
  - **UPPER()**: Converts a string to uppercase.
    - **Example**: 
      ```sql
      SELECT UPPER(StudentName) FROM Students;
      ```
  - **LOWER()**: Converts a string to lowercase.
    - **Example**: 
      ```sql
      SELECT LOWER(StudentName) FROM Students;
      ```
  - **LENGTH()**: Returns the length of a string.
    - **Example**: 
      ```sql
      SELECT LENGTH(StudentName) FROM Students;
      ```
  - **SUBSTRING()**: Extracts a substring from a string.
    - **Example**: 
      ```sql
      SELECT SUBSTRING(StudentName, 1, 3) FROM Students;
      ```

### 5.3 Date Functions
- **Definition**: Functions that perform operations on date and time data types.
- **Common Date Functions**:
  - **NOW()**: Returns the current date and time.
    - **Example**: 
      ```sql
      SELECT NOW();
      ```
  - **DATE()**: Extracts the date part from a date/time expression.
    - **Example**: 
      ```sql
      SELECT DATE(NOW());
      ```
  - **YEAR()**: Returns the year from a date.
    - **Example**: 
      ```sql
      SELECT YEAR(DateOfBirth) FROM Students;
      ```

## 6. SQL Joins
- **Definition**: Joins are used to combine rows from two or more tables based on a related column.
- **Types of Joins**:
  - **INNER JOIN**: Returns records that have matching values in both tables.
    - **Example**: 
      ```sql
      SELECT Students.StudentName, Courses.CourseName 
      FROM Students 
      INNER JOIN Enrollments ON Students.StudentID = Enrollments.StudentID 
      INNER JOIN Courses ON Enrollments.CourseID = Courses.CourseID;
      ```
  - **LEFT JOIN**: Returns all records from the left table and matched records from the right table. If no match, NULL values are returned for the right table.
    - **Example**: 
      ```sql
      SELECT Students.StudentName, Courses.CourseName 
      FROM Students 
      LEFT JOIN Enrollments ON Students.StudentID = Enrollments.StudentID 
      LEFT JOIN Courses ON Enrollments.CourseID = Courses.CourseID;
      ```
  - **RIGHT JOIN**: Returns all records from the right table and matched records from the left table. If no match, NULL values are returned for the left table.
    - **Example**: 
      ```sql
      SELECT Students.StudentName, Courses.CourseName 
      FROM Students 
      RIGHT JOIN Enrollments ON Students.StudentID = Enrollments.StudentID 
      RIGHT JOIN Courses ON Enrollments.CourseID = Courses.CourseID;
      ```
  - **FULL OUTER JOIN**: Returns all records when there is a match in either left or right table records.
    - **Example**: 
      ```sql
      SELECT Students.StudentName, Courses.CourseName 
      FROM Students 
      FULL OUTER JOIN Enrollments ON Students.StudentID = Enrollments.StudentID 
      FULL OUTER JOIN Courses ON Enrollments.CourseID = Courses.CourseID;
      ```

## 7. Data Integrity
- **Definition**: Data integrity refers to the accuracy and consistency of data within a database.
- **Types of Data Integrity**:
  - **Entity Integrity**: Ensures that each entity has a unique identifier (primary key) and that no two records can have the same primary key value.
  - **Referential Integrity**: Ensures that relationships between tables remain consistent. For example, if a student is deleted from the Students table, all related records in the Enrollments table should also be removed to maintain referential integrity.
  - **Domain Integrity**: Ensures that all values in a column fall within a defined set of valid values (e.g., a column for age should only contain positive integers).

## 8. Conclusion
- **Key Takeaways**:
  - SQL is a powerful tool for managing and manipulating relational databases.
  - Understanding SQL commands, functions, and data integrity is crucial for effective database management.
  - Proper use of SQL can lead to efficient data retrieval and manipulation, ensuring data accuracy and consistency.

## 9. Exercises
1. **Write SQL Queries**: Write SQL queries to perform the following operations:
   - Retrieve all records from the Students table.
   - Insert a new student record into the Students table.
   - Update the name of a student in the Students table.
   - Delete a student record from the Students table.
2. **Normalization Practice**: Given an unnormalized table, apply normalization to achieve at least 3NF.
3. **Join Operations**: Write SQL queries to demonstrate different types of joins using the Students, Enrollments, and Courses tables.

