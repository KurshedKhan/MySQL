Here are some **important and basic string functions in MySQL** that are commonly used:

---

### 🔹 **1. `LENGTH(str)`**

* Returns the length of the string in bytes.

```sql
SELECT LENGTH('MySQL');  -- Output: 5
```

---

### 🔹 **2. `CHAR_LENGTH(str)` / `CHARACTER_LENGTH(str)`**

* Returns the number of characters (not bytes).

```sql
SELECT CHAR_LENGTH('MySQL');  -- Output: 5
```

---

### 🔹 **3. `CONCAT(str1, str2, …)`**

* Joins strings together.

```sql
SELECT CONCAT('Hello', ' ', 'World');  -- Output: Hello World
```

---

### 🔹 **4. `CONCAT_WS(separator, str1, str2, …)`**

* Same as `CONCAT`, but adds a separator.

```sql
SELECT CONCAT_WS('-', '2025', '05', '22');  -- Output: 2025-05-22
```

---

### 🔹 **5. `LOWER(str)` / `LCASE(str)`**

* Converts to lowercase.

```sql
SELECT LOWER('MYSQL');  -- Output: mysql
```

---

### 🔹 **6. `UPPER(str)` / `UCASE(str)`**

* Converts to uppercase.

```sql
SELECT UPPER('mysql');  -- Output: MYSQL
```

---

### 🔹 **7. `TRIM(str)`**

* Removes leading and trailing spaces.

```sql
SELECT TRIM('   Hello   ');  -- Output: Hello
```

---

### 🔹 **8. `LTRIM(str)` and `RTRIM(str)`**

* Removes leading (`LTRIM`) or trailing (`RTRIM`) spaces.

```sql
SELECT LTRIM('   Hello');  -- Output: Hello
SELECT RTRIM('Hello   ');  -- Output: Hello
```

---

### 🔹 **9. `SUBSTRING(str, start, length)` or `SUBSTR()`**

* Extracts a part of the string.

```sql
SELECT SUBSTRING('MySQL Tutorial', 1, 5);  -- Output: MySQL
```

---

### 🔹 **10. `REPLACE(str, from_str, to_str)`**

* Replaces part of a string.

```sql
SELECT REPLACE('I love Java', 'Java', 'MySQL');  -- Output: I love MySQL
```

---

### 🔹 **11. `INSTR(str, substr)`**

* Returns the position of the substring.

```sql
SELECT INSTR('MySQL Tutorial', 'Tutorial');  -- Output: 7
```

---

### 🔹 **12. `REVERSE(str)`**

* Reverses the string.

```sql
SELECT REVERSE('MySQL');  -- Output: LQSyM
```

---

### 🔹 **13. `LEFT(str, length)` / `RIGHT(str, length)`**

* Gets a certain number of characters from the start or end.

```sql
SELECT LEFT('MySQL', 2);   -- Output: My
SELECT RIGHT('MySQL', 3);  -- Output: SQL
```

---

### 🔹 **14. `LPAD(str, len, padstr)` / `RPAD(str, len, padstr)`**

* Pads string on the left or right with another string.

```sql
SELECT LPAD('123', 5, '0');  -- Output: 00123
SELECT RPAD('123', 5, '0');  -- Output: 12300
```

---

### 🔹 **15. `FORMAT(number, decimal_places)`**

* Formats a number with commas.

```sql
SELECT FORMAT(1234567.89, 2);  -- Output: 1,234,567.89
```


