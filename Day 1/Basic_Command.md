# 🗄️ MySQL Database Commands Cheat Sheet

Learn essential MySQL database commands with practical examples! Perfect for beginners and pros alike.

---

## 🚀 **1. Create a Database**
**Command**: `CREATE DATABASE`  
**Purpose**: Build a new database to store your data.  

### Syntax:
```sql
CREATE DATABASE database_name;
```

### Example:
```sql
CREATE DATABASE my_shop;
```
**Explanation**:  
Creates a database named `my_shop` to store e-commerce data.  

**Pro Tip**:  
🔸 Always use **meaningful names** (e.g., `school_db`, `blog_data`).  
🔸 Avoid special characters or spaces. Use underscores (`_`) instead.

---

## 📂 **2. Use a Database**
**Command**: `USE`  
**Purpose**: Switch to a specific database to work inside it.  

### Syntax:
```sql
USE database_name;
```

### Example:
```sql
USE my_shop;
```
**Explanation**:  
Sets `my_shop` as the **active database**. All subsequent commands (like `CREATE TABLE`) will apply to this database.  

**Note**:  
❌ Error if the database doesn’t exist. Always create it first!

---

## 🔍 **3. Show Current Database**
**Command**: `SELECT DATABASE()`  
**Purpose**: Check which database you’re currently using.  

### Syntax:
```sql
SELECT DATABASE();
```

### Example Output:
```
+------------+
| DATABASE() |
+------------+
| my_shop    |
+------------+
```
**Explanation**:  
Returns the name of the **active database**. Helpful if you forget which one you’re working in!  

---

## 💣 **4. Drop a Database**
**Command**: `DROP DATABASE`  
**Purpose**: Permanently delete a database and all its data. **Use with caution!**  

### Syntax:
```sql
DROP DATABASE database_name;
```

### Example:
```sql
DROP DATABASE old_archive;
```
**Explanation**:  
Deletes the `old_archive` database.  

⚠️ **Warning**:  
🔸 This action is **irreversible**.  
🔸 Double-check the database name before running!  

---

## 📋 **5. List All Databases**
**Command**: `SHOW DATABASES`  
**Purpose**: View all databases on your MySQL server.  

### Syntax:
```sql
SHOW DATABASES;
```

### Example Output:
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| my_shop            |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```
**Explanation**:  
Lists **all databases**, including system databases like `mysql` and `information_schema`.

---

## 🎓 **Summary**
| Command               | Use Case                                | Example                     |
|-----------------------|-----------------------------------------|-----------------------------|
| `CREATE DATABASE`     | Create a new database                   | `CREATE DATABASE school;`   |
| `USE`                 | Switch to a database                    | `USE school;`               |
| `SELECT DATABASE()`   | Check the active database               | `SELECT DATABASE();`        |
| `DROP DATABASE`       | Delete a database                       | `DROP DATABASE temp_data;`  |
| `SHOW DATABASES`      | List all databases                      | `SHOW DATABASES;`           |

---

**Fun Fact**:  
MySQL’s name combines **“My”** (the co-founder’s daughter’s name) and **“SQL”**. 🤯  

🚨 **Always back up your data before dropping databases!**  
