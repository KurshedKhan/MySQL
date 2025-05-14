**MySQL Data Types Overview**

MySQL supports various data types to store different kinds of information efficiently. Below is a structured breakdown:

### 1. **Numeric Types**
- **Integer Types**:
  - `TINYINT`: 1 byte (-128 to 127 or 0-255 UNSIGNED).  
    Example: `age TINYINT UNSIGNED`.
  - `SMALLINT`: 2 bytes (-32,768 to 32,767).  
    Example: `number_of_students SMALLINT`.
  - `MEDIUMINT`: 3 bytes (-8.3 million to 8.3 million).  
    Example: `population MEDIUMINT`.
  - `INT`: 4 bytes (-2.1 billion to 2.1 billion).  
    Example: `user_id INT`.
  - `BIGINT`: 8 bytes (large range).  
    Example: `transaction_id BIGINT`.

- **Fixed-Point**:
  - `DECIMAL(precision, scale)` or `NUMERIC`: Exact decimal values.  
    Example: `price DECIMAL(10,2)` for currency.

- **Floating-Point**:
  - `FLOAT`: 4 bytes (approximate, 7 decimal digits).  
    Example: `temperature FLOAT`.
  - `DOUBLE`: 8 bytes (approximate, 15 decimal digits).  
    Example: `scientific_data DOUBLE`.

### 2. **String/Text Types**
- **Fixed/Variable Length**:
  - `CHAR(n)`: Fixed length (0-255), padded with spaces.  
    Example: `country_code CHAR(2)`.
  - `VARCHAR(n)`: Variable length (0-65,535 characters).  
    Example: `email VARCHAR(255)`.

- **Text Types**:
  - `TINYTEXT`: 255 characters.  
    Example: `short_note TINYTEXT`.
  - `TEXT`: 65,535 characters.  
    Example: `article_content TEXT`.
  - `MEDIUMTEXT`: 16 million characters.  
    Example: `book_content MEDIUMTEXT`.
  - `LONGTEXT`: 4GB of text.  
    Example: `log_data LONGTEXT`.

- **Binary Data**:
  - `BLOB` types (`TINYBLOB`, `BLOB`, `MEDIUMBLOB`, `LONGBLOB`): Store binary data (e.g., images, files).

- **Special Types**:
  - `ENUM('val1', 'val2')`: Choose one from a list.  
    Example: `status ENUM('active', 'inactive')`.
  - `SET('val1', 'val2')`: Choose multiple values.  
    Example: `tags SET('red', 'green', 'blue')`.

### 3. **Date and Time Types**
- `DATE`: Stores `YYYY-MM-DD`.  
  Example: `birthdate DATE`.
- `TIME`: Stores `hh:mm:ss`.  
  Example: `meeting_time TIME`.
- `DATETIME`: Combines date and time (`YYYY-MM-DD hh:mm:ss`).  
  Example: `created_at DATETIME`.
- `TIMESTAMP`: UTC date/time (range: 1970-2038), auto-converts timezones.  
  Example: `last_updated TIMESTAMP`.
- `YEAR(4)`: 4-digit year.  
  Example: `graduation_year YEAR`.

### 4. **Spatial Types**
- For geographic data (e.g., `GEOMETRY`, `POINT`, `LINESTRING`, `POLYGON`).  
  Example: `location POINT`.

### 5. **JSON Type**
- `JSON`: Store and validate JSON data (MySQL 5.7.8+).  
  Example: `user_preferences JSON`.

### Key Considerations:
- **Storage Efficiency**: Use the smallest data type that fits your data (e.g., `TINYINT` instead of `INT` for small numbers).
- **Fixed vs. Variable**: Prefer `CHAR` for fixed-length strings (e.g., MD5 hashes) and `VARCHAR` for variable lengths.
- **Date/Time**: Use `DATETIME` for general purposes and `TIMESTAMP` for timezone-sensitive tracking.
- **JSON Validation**: The `JSON` type ensures valid JSON and allows efficient querying.

### Example Table:
```sql
CREATE TABLE users (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50) UNIQUE,
  birthdate DATE,
  active_status ENUM('active', 'inactive'),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  preferences JSON
);
```

**Note**: Always choose data types based on data requirements to optimize performance and storage! 🚀