To **insert (add)** and **delete (drop)** a column in an SQL table, use the `ALTER TABLE` statement. Below are the standard syntaxes and examples:

---

### **1. Inserting/Adding a New Column**
Use the `ADD COLUMN` clause to add a new column to an existing table.

#### **Syntax**:
```sql
ALTER TABLE table_name
ADD COLUMN column_name data_type [constraints];
```

#### **Examples**:
1. Add a column without constraints:
   ```sql
   ALTER TABLE employees
   ADD COLUMN email VARCHAR(255);
   ```

2. Add a column with constraints (e.g., `NOT NULL`, `DEFAULT`):
   ```sql
   ALTER TABLE employees
   ADD COLUMN hire_date DATE NOT NULL DEFAULT CURRENT_DATE;
   ```

---

### **2. Deleting/Dropping a Column**
Use the `DROP COLUMN` clause to remove an existing column.

#### **Syntax**:
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

#### **Examples**:
1. Drop a single column:
   ```sql
   ALTER TABLE employees
   DROP COLUMN email;
   ```

---

### **Important Notes**:
1. **Database Compatibility**:
   - Some databases (e.g., **SQLite**) do not support dropping columns directly. You may need to create a new table and migrate data.
   - In **SQL Server**, use `ALTER TABLE ... DROP COLUMN`.
   - In **MySQL**, use `ALTER TABLE ... DROP COLUMN`.

2. **Data Loss**:
   - Dropping a column permanently deletes all data in that column. Always back up your data first.

3. **Constraints**:
   - If a column is referenced by constraints (e.g., foreign keys), you must remove those constraints first.

---

### **Example Workflow**:
1. Add a `phone_number` column:
   ```sql
   ALTER TABLE customers
   ADD COLUMN phone_number VARCHAR(15);
   ```

2. Drop the `phone_number` column:
   ```sql
   ALTER TABLE customers
   DROP COLUMN phone_number;
   ```

---