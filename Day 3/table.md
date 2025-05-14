To create a table in MySQL, you use the `CREATE TABLE` statement. Below is a detailed explanation of the syntax, components, and an example.

---

### **Basic Syntax**
```sql
CREATE TABLE [IF NOT EXISTS] table_name (
    column1 datatype [constraints],
    column2 datatype [constraints],
    ...
    [table_constraints]
) [ENGINE=storage_engine] [DEFAULT CHARSET=charset_name];
```

---

### **Components Explained**
1. **`CREATE TABLE`**: Command to create a new table.
2. **`IF NOT EXISTS`**: Optional clause to avoid errors if the table already exists.
3. **`table_name`**: Name of the table (use backticks if the name contains special characters, e.g., `` `order-details` ``).
4. **Columns**:
   - **`column_name`**: Name of the column.
   - **`datatype`**: Data type (e.g., `INT`, `VARCHAR`, `DATE`).
   - **Constraints**: Rules for the column (e.g., `PRIMARY KEY`, `NOT NULL`).
5. **Table Constraints**: Additional rules (e.g., `FOREIGN KEY`).
6. **Storage Engine**: Optional (default: `InnoDB`). Others include `MyISAM`, `MEMORY`.
7. **Character Set**: Optional (default: `utf8mb4`).

---

### **Example Table: `users`**
```sql
CREATE TABLE IF NOT EXISTS users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    email VARCHAR(100) NOT NULL UNIQUE,
    date_of_birth DATE,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
    is_active TINYINT(1) DEFAULT 1
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

---

### **Breakdown of Columns & Constraints**
| Column Name       | Data Type       | Constraints/Explanation                                                                 |
|-------------------|-----------------|-----------------------------------------------------------------------------------------|
| `user_id`         | `INT`           | `AUTO_INCREMENT`: Auto-generates unique IDs. `PRIMARY KEY`: Uniquely identifies each row. |
| `username`        | `VARCHAR(50)`   | `NOT NULL`: Must have a value. `UNIQUE`: No duplicate usernames allowed.                |
| `email`           | `VARCHAR(100)`  | `NOT NULL` + `UNIQUE`: Ensures valid and unique emails.                                 |
| `date_of_birth`   | `DATE`          | Optional field (can be `NULL`).                                                         |
| `created_at`      | `DATETIME`      | `DEFAULT CURRENT_TIMESTAMP`: Automatically sets the creation date/time.                 |
| `is_active`       | `TINYINT(1)`    | `DEFAULT 1`: Boolean-like field (0 = inactive, 1 = active).                             |

---

### **Common Data Types**
1. **Numeric**: 
   - `INT`: Integer values.
   - `DECIMAL(10,2)`: Fixed-point numbers (e.g., prices).
2. **String**:
   - `VARCHAR(n)`: Variable-length strings (max length `n`).
   - `TEXT`: Long-form text.
3. **Date/Time**:
   - `DATE`: `YYYY-MM-DD`.
   - `DATETIME`: `YYYY-MM-DD HH:MM:SS`.
4. **Boolean**:
   - `TINYINT(1)`: 0 (false) or 1 (true).

---

### **Key Constraints**
| Constraint         | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `PRIMARY KEY`      | Uniquely identifies a row (e.g., `user_id`).                                |
| `FOREIGN KEY`      | Links to a `PRIMARY KEY` in another table (enforces referential integrity). |
| `NOT NULL`         | Column cannot have `NULL` values.                                           |
| `UNIQUE`           | All values in the column must be distinct.                                  |
| `DEFAULT`          | Sets a default value if no value is provided.                               |
| `AUTO_INCREMENT`   | Automatically increments integer values (for primary keys).                |

---

### **Example with Foreign Key**
Create an `orders` table linked to `users`:
```sql
CREATE TABLE orders (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    amount DECIMAL(10,2) NOT NULL,
    order_date DATE,
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);
```

---

### **Important Notes**
1. Use **backticks** for table/column names with spaces or reserved keywords.
2. Plan your table structure carefully (e.g., data types, constraints) before creation.
3. Use `DESCRIBE table_name;` to view the table structure.
4. Insert data with `INSERT INTO table_name (column1, column2) VALUES (value1, value2);`.

---

### **Common Errors**
- Forgetting commas between columns.
- Missing `NOT NULL` for mandatory fields.
- Incorrect foreign key references.
