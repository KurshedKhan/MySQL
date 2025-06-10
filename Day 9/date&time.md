### ✅ **1. Data Types for Date and Time**

| Data Type   | Description                            | Example                       |
| ----------- | -------------------------------------- | ----------------------------- |
| `DATE`      | Stores only date (YYYY-MM-DD)          | `'2025-06-10'`                |
| `TIME`      | Stores only time (HH\:MM\:SS)          | `'13:45:30'`                  |
| `DATETIME`  | Stores both date and time              | `'2025-06-10 13:45:30'`       |
| `TIMESTAMP` | Stores date & time, with timezone info | `'2025-06-10 13:45:30+00:00'` |
| `YEAR`      | Stores year (2-digit or 4-digit)       | `2025`                        |

---

### ✅ **2. Functions to Get Current Date/Time**

| Function    | Output Example        | Description                |
| ----------- | --------------------- | -------------------------- |
| `NOW()`     | `2025-06-10 11:24:00` | Current date and time      |
| `CURDATE()` | `2025-06-10`          | Current date only          |
| `CURTIME()` | `11:24:00`            | Current time only          |
| `SYSDATE()` | Similar to `NOW()`    | Current system date & time |

---

### ✅ **3. Insert Date & Time**

```sql
INSERT INTO events (event_name, event_date)
VALUES ('Meeting', '2025-06-10 14:00:00');
```

---

### ✅ **4. Extracting Parts**

```sql
SELECT
  YEAR(event_date),
  MONTH(event_date),
  DAY(event_date),
  HOUR(event_date),
  MINUTE(event_date),
  SECOND(event_date)
FROM events;
```

---

### ✅ **5. Date Arithmetic**

```sql
-- Add 5 days
SELECT DATE_ADD('2025-06-10', INTERVAL 5 DAY);  -- 2025-06-15

-- Subtract 2 months
SELECT DATE_SUB('2025-06-10', INTERVAL 2 MONTH); -- 2025-04-10
```

---

### ✅ **6. Date Format**

```sql
SELECT DATE_FORMAT(NOW(), '%d-%m-%Y %H:%i:%s');
-- Output: 10-06-2025 11:24:00
```

---