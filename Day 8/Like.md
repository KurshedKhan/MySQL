The `LIKE` keyword in SQL is used to search for a **pattern in a column's values** using **wildcards**:

* `%` = matches **any number of characters**
* `_` = matches **a single character**

---

### 🔹 1. **Find employees whose first name starts with 'R'**

```sql
SELECT * FROM employees
WHERE fname LIKE 'R%';
```

---

### 🔹 2. **Find employees whose last name ends with 'n'**

```sql
SELECT * FROM employees
WHERE lname LIKE '%n';
```

---

### 🔹 3. **Find employees whose designation contains 'soci'**

```sql
SELECT * FROM employees
WHERE desig LIKE '%soci%';
```

---

### 🔹 4. **Find employees whose department has exactly 5 letters and starts with 'L'**

```sql
SELECT * FROM employees
WHERE dept LIKE 'L____';
```

---
