## 1. Creating a Table

### Basic
```sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    email VARCHAR(100)
);
```

### Advanced (with Constraints)
```sql
CREATE TABLE employees (
    emp_id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100) NOT NULL,
    salary DECIMAL(10,2) CHECK (salary > 0),
    department VARCHAR(50) DEFAULT 'General',
    joined_date DATE,
    UNIQUE (email)
);
```

---

## 2. Checking Table Structure

### Basic
```sql
DESC users;  -- MySQL
```

### Advanced
```sql
SELECT column_name, data_type 
FROM information_schema.columns
WHERE table_name = 'employees';  -- Cross-platform
```

---

## 3. Inserting Single Data

### Basic
```sql
INSERT INTO users (id, name, email)
VALUES (1, 'John Doe', 'john@example.com');
```

### Advanced (Using Functions)
```sql
INSERT INTO employees (full_name, salary, joined_date)
VALUES ('Alice Smith', 75000.00, CURDATE());
```

---

## 4. Inserting Multiple Data

### Basic
```sql
INSERT INTO users (id, name, email)
VALUES 
    (2, 'Jane Smith', 'jane@example.com'),
    (3, 'Bob Wilson', 'bob@example.com');
```

### Advanced (Bulk Insert)
```sql
INSERT INTO employees (full_name, salary)
SELECT name, salary FROM temp_employees WHERE status = 'active';
```

---

## 5. Reading Data

### Basic
```sql
SELECT * FROM users;
```

### Advanced (with Joins)
```sql
SELECT e.full_name, d.department_name 
FROM employees e
JOIN departments d ON e.department_id = d.dept_id;
```

---

## 6. Read Specific Column

### Basic
```sql
SELECT name, email FROM users;
```

### Advanced (Aliases)
```sql
SELECT 
    full_name AS "Employee Name",
    salary * 12 AS "Annual Salary"
FROM employees;
```

---

## 7. Conditional Data Retrieval

### Basic (Single Condition)
```sql
SELECT * FROM users WHERE id = 2;
```

### Advanced (Multiple Conditions)
```sql
SELECT * FROM employees
WHERE 
    department = 'Sales' 
    AND salary > 50000
    AND joined_date BETWEEN '2023-01-01' AND '2023-12-31';
```

---

## 8. Modifying Data

### Basic Update
```sql
UPDATE users
SET email = 'john.new@example.com'
WHERE id = 1;
```

### Advanced Update (Multiple Columns/Conditions)
```sql
UPDATE employees
SET 
    salary = salary * 1.05,
    department = 'Senior Marketing'
WHERE 
    department = 'Marketing'
    AND joined_date < '2020-01-01';
```

---

## Bonus: Transaction Example
```sql
START TRANSACTION;

INSERT INTO orders (order_id, customer_id, amount)
VALUES (1001, 456, 199.99);

UPDATE inventory
SET stock = stock - 1
WHERE product_id = 789;

COMMIT;
```

---

## Pro Tips:
1. Always use `WHERE` clause with UPDATE/DELETE
2. Use transactions for critical operations
3. Create indexes on frequently searched columns
4. Normalize your database structure
5. Use EXPLAIN to analyze query performance
```