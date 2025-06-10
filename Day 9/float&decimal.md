## 🔢 FLOAT vs DECIMAL in SQL

| Feature       | `FLOAT` (or `REAL`)                             | `DECIMAL` (or `NUMERIC`)                      |
| ------------- | ----------------------------------------------- | --------------------------------------------- |
| **Type**      | Approximate numeric                             | Exact numeric                                 |
| **Precision** | Limited precision, may round values             | High precision, no rounding issues            |
| **Storage**   | Less storage space                              | More storage space                            |
| **Use case**  | Scientific data, sensor data, fast calculations | Money, prices, finance where accuracy matters |
| **Example**   | `FLOAT(7, 4)` → `123.4567` (approximate)        | `DECIMAL(7, 4)` → `123.4567` (exact)          |

---

### ✅ Syntax

#### FLOAT

```sql
CREATE TABLE sample (
  value FLOAT(7, 4)
);
```

#### DECIMAL

```sql
CREATE TABLE finance (
  price DECIMAL(10, 2)  -- up to 10 digits, 2 after decimal
);
```

---

### ⚠️ Key Differences (Simple Words)

| Point              | FLOAT             | DECIMAL           |
| ------------------ | ----------------- | ----------------- |
| Rounded values     | Yes (internally)  | No (exact)        |
| Money calculations | ❌ Not recommended | ✅ Perfect         |
| Fast calculations  | ✅                 | ❌ Slightly slower |

---

### 🎯 Summary

* Use **`DECIMAL`** when you need **accuracy** (e.g., money).
* Use **`FLOAT`** when you need **speed** and can tolerate **minor rounding errors**.

---

