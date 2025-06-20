In SQL (Structured Query Language), **relationships** refer to how tables are connected to each other based on **primary keys** and **foreign keys**. These relationships help maintain **data integrity** and allow us to retrieve related data using **joins**.

---

### 🔗 Types of Relationships in SQL:

#### 1. **One-to-One (1:1)**

* One row in Table A is related to **only one** row in Table B.
* Example:
  `User` table and `UserProfile` table
  Each user has one profile.

#### 2. **One-to-Many (1\:N) \[Most Common]**

* One row in Table A is related to **many** rows in Table B.
* Example:
  `Department` table and `Employee` table
  One department has many employees.

#### 3. **Many-to-Many (M\:N)**

* Many rows in Table A are related to many rows in Table B.
* Requires a **junction (bridge)** table with foreign keys from both tables.
* Example:
  `Student` table and `Course` table → use `StudentCourse` table.

---

### 🔑 Keys Used in Relationships:

| Key Type        | Purpose                                                              |
| --------------- | -------------------------------------------------------------------- |
| **Primary Key** | Uniquely identifies each row in a table                              |
| **Foreign Key** | A field in one table that refers to the primary key in another table |

---

### 🧪 Example:

```sql
-- Table: Department
CREATE TABLE Department (
  dept_id INT PRIMARY KEY,
  dept_name VARCHAR(50)
);

-- Table: Employee (One-to-Many)
CREATE TABLE Employee (
  emp_id INT PRIMARY KEY,
  emp_name VARCHAR(50),
  dept_id INT,
  FOREIGN KEY (dept_id) REFERENCES Department(dept_id)
);
```

---

### 🧩 Retrieving Related Data: (Using JOIN)

```sql
SELECT Employee.emp_name, Department.dept_name
FROM Employee
JOIN Department ON Employee.dept_id = Department.dept_id;
```

---

