To sort the data using `ORDER BY`, here are some examples based on the table:

---

### 🔹 1. **Order by `fname` (First Name) in Ascending Order**

```sql
SELECT * FROM employees
ORDER BY fname ASC;
```

---

### 🔹 2. **Order by `emp_id` in Descending Order**

```sql
SELECT * FROM employees
ORDER BY emp_id DESC;
```

---

### 🔹 3. **Order by `dept`, then by `desig`**

```sql
SELECT * FROM employees
ORDER BY dept ASC, desig ASC;
```

---

### 🔹 4. **Order by `desig` in descending order**

```sql
SELECT * FROM employees
ORDER BY desig DESC;
```

---

