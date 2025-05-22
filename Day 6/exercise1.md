**Student Exercise: Database Management**  
**Instructions:** Perform the following tasks using SQL commands. Write your answers in the space provided.  

---

### **Task 1: Create Database and Table**  
Create a database named `bank_db`. Inside it, create a table `employees` with the following structure:  

| Column | Constraints |  
|--------|-------------|  
| emp_id | - Primary key (no duplicates, no null) <br> - Auto-increment |  
| name   | - Not null |  
| desig  | - Default value: 'Probation' |  
| dept   | - No constraints |  

---

### **Task 2: Insert Data**  
Insert the following records into the `employees` table. Include the `emp_id` explicitly:  

| emp_id | name    | desig        | dept    |  
|--------|---------|--------------|---------|  
| 101    | Raju    | Manager      | Loan    |  
| 102    | Sham    | Cashier      | Cash    |  
| 103    | Paul    | Associate    | Loan    |  
| 104    | Alex    | Accountant   | Account |  
| 105    | Victor   | Associate    | Deposit |  

---

### **Task 3: Display Data**  
Write a SQL query to display all columns and records from the `employees` table.  

---

### **Task 4: Update Data**  
Update the department of employee `Paul` (emp_id = 103) from `Loan` to `IT`.  

---

### **Task 5: Delete Data**  
Delete the record where the department is `IT`.  

---
 