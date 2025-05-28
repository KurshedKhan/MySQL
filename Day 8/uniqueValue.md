The `DISTINCT` keyword is used in SQL to return **only unique (different) values**.

Here are some examples using your `employees` table:

---

### 🔹 1. **Get all unique designations (`desig`)**

```sql
SELECT DISTINCT desig FROM employees;
```

✅ Output:

```
Manager
Cashier
Associate
Accountant
```

---

### 🔹 2. **Get all unique departments (`dept`)**

```sql
SELECT DISTINCT dept FROM employees;
```

✅ Output:

```
Loan
Cash
Account
Deposit
```

---

### 🔹 3. **Get all unique combinations of designation and department**

```sql
SELECT DISTINCT desig, dept FROM employees;
```

---

### 🔹 4. **Get all unique first names (`fname`)**

```sql
SELECT DISTINCT fname FROM employees;
```

---
