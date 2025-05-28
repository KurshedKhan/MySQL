Based on the table shown in your image, here's the SQL code to create the table and insert the data:

### ✅ SQL `CREATE TABLE` Statement

```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY,
    fname VARCHAR(50),
    lname VARCHAR(50),
    desig VARCHAR(50),
    dept VARCHAR(50)
);
```

### ✅ SQL `INSERT INTO` Statements

```sql
INSERT INTO employees (emp_id, fname, lname, desig, dept) VALUES
(101, 'Raju', 'Rastogi', 'Manager', 'Loan'),
(102, 'Sham', 'Mohan', 'Cashier', 'Cash'),
(103, 'Baburao', 'Apte', 'Associate', 'Loan'),
(104, 'Paul', 'Philip', 'Accountant', 'Account'),
(105, 'Alex', 'Watt', 'Associate', 'Deposit');
```
