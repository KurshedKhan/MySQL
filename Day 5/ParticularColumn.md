To insert values into **specific columns** (not all columns) of a table in SQL, you can explicitly specify the target columns in the `INSERT INTO` statement. This way, only the listed columns will receive values, and the remaining columns will either be set to their default values (if defined) or `NULL` (if allowed).

---

### **Syntax**:
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

- **Specify the columns** you want to populate in parentheses after the table name.
- **Provide values** in the same order as the specified columns.

---

### **Example**:
Let's say you have a table `employees` with columns:
- `id` (auto-incremented)
- `name` (NOT NULL)
- `email` (nullable)
- `salary` (nullable)
- `hire_date` (DEFAULT: CURRENT_DATE)

#### **Insert data into specific columns**:
```sql
-- Insert values only into 'name' and 'email' columns
INSERT INTO employees (name, email)
VALUES ('John Doe', 'john@example.com');
```

#### **Result**:
- `id`: Auto-incremented (e.g., 1).
- `name`: 'John Doe' (explicitly set).
- `email`: 'john@example.com' (explicitly set).
- `salary`: `NULL` (since not specified).
- `hire_date`: `CURRENT_DATE` (default value used).

---

### **Key Points**:
1. **Order of Columns**:
   - The order of values in `VALUES` must match the order of the specified columns.
   - Example:
     ```sql
     INSERT INTO employees (email, name) -- Wrong order
     VALUES ('John Doe', 'john@example.com'); -- Error: type mismatch
     ```

2. **Mandatory Columns**:
   - If a column has a `NOT NULL` constraint and no default value, you **must include it** in the `INSERT` statement.
   - Example:
     ```sql
     -- This will fail if 'name' is NOT NULL and has no default:
     INSERT INTO employees (email) VALUES ('john@example.com');
     ```

3. **Default Values**:
   - If a column has a `DEFAULT` constraint, it will automatically use that value if not specified in the `INSERT`.

---

### **Use Cases**:
1. Insert data when some columns have defaults (e.g., auto-incremented `id`).
2. Skip nullable columns that don’t require data.
3. Insert partial data first and update other columns later.

---

### **Comparison: Inserting into All Columns**:
If you omit the column list, you **must** provide values for **all columns** (in the order they were defined in the table):
```sql
-- Requires values for all columns (including 'id' and 'hire_date'):
INSERT INTO employees
VALUES (1, 'John Doe', 'john@example.com', 50000, '2023-10-25');
```

---

### **Important**:
Always check the table structure (using `DESCRIBE table_name;` in MySQL or `sp_help table_name` in SQL Server) to know which columns are mandatory or have default values.