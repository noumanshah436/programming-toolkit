Here is a comprehensive list of common SQL commands for PostgreSQL, organized by category:

### **1. Database Commands**
- **Create a Database**:
   ```sql
   CREATE DATABASE dbname;
   ```

- **Connect to a Database**:
   ```sql
   \c dbname;
   ```

- **List Databases**:
   ```sql
   \l
   ```

- **Drop a Database**:
   ```sql
   DROP DATABASE dbname;
   ```

---

### **2. Table Commands**
- **Create a Table**:
   ```sql
   CREATE TABLE table_name (
       column_name1 data_type constraints,
       column_name2 data_type constraints,
       ...
   );
   ```

- **List Tables**:
   ```sql
   \dt
   ```

- **Describe Table Schema**:
   ```sql
   \d table_name;
   ```

- **Drop a Table**:
   ```sql
   DROP TABLE table_name;
   ```

- **Alter Table (Add a Column)**:
   ```sql
   ALTER TABLE table_name
   ADD COLUMN column_name data_type;
   ```

- **Alter Table (Drop a Column)**:
   ```sql
   ALTER TABLE table_name
   DROP COLUMN column_name;
   ```

---

### **3. Data Manipulation Commands**
- **Insert Data**:
   ```sql
   INSERT INTO table_name (column1, column2, ...)
   VALUES (value1, value2, ...);
   ```

- **Select Data**:
   ```sql
   SELECT column1, column2, ...
   FROM table_name
   WHERE condition;
   ```

- **Update Data**:
   ```sql
   UPDATE table_name
   SET column1 = value1, column2 = value2
   WHERE condition;
   ```

- **Delete Data**:
   ```sql
   DELETE FROM table_name
   WHERE condition;
   ```

---

### **4. Constraints & Keys**
- **Create a Primary Key**:
   ```sql
   CREATE TABLE table_name (
       column_name data_type PRIMARY KEY
   );
   ```

- **Create a Foreign Key**:
   ```sql
   CREATE TABLE table_name (
       column_name data_type,
       CONSTRAINT fk_name FOREIGN KEY (column_name)
       REFERENCES other_table (column_name)
   );
   ```

- **Unique Constraint**:
   ```sql
   CREATE TABLE table_name (
       column_name data_type UNIQUE
   );
   ```

---

### **5. Indexing**
- **Create an Index**:
   ```sql
   CREATE INDEX index_name
   ON table_name (column_name);
   ```

- **Drop an Index**:
   ```sql
   DROP INDEX index_name;
   ```

---

### **6. User Management**
- **Create a User**:
   ```sql
   CREATE USER username WITH PASSWORD 'password';
   ```

- **Grant Privileges**:
   ```sql
   GRANT ALL PRIVILEGES ON DATABASE dbname TO username;
   ```

- **Revoke Privileges**:
   ```sql
   REVOKE ALL PRIVILEGES ON DATABASE dbname FROM username;
   ```

- **Drop a User**:
   ```sql
   DROP USER username;
   ```

---

### **7. Views**
- **Create a View**:
   ```sql
   CREATE VIEW view_name AS
   SELECT column1, column2, ...
   FROM table_name
   WHERE condition;
   ```

- **Drop a View**:
   ```sql
   DROP VIEW view_name;
   ```

---

### **8. Transactions**
- **Begin a Transaction**:
   ```sql
   BEGIN;
   ```

- **Commit a Transaction**:
   ```sql
   COMMIT;
   ```

- **Rollback a Transaction**:
   ```sql
   ROLLBACK;
   ```

---

### **9. Sequences**
- **Create a Sequence**:
   ```sql
   CREATE SEQUENCE sequence_name
   START WITH 1
   INCREMENT BY 1;
   ```

- **Use a Sequence**:
   ```sql
   INSERT INTO table_name (column_name)
   VALUES (nextval('sequence_name'));
   ```

- **Drop a Sequence**:
   ```sql
   DROP SEQUENCE sequence_name;
   ```

---

### **10. Aggregate Functions**
- **Count**:
   ```sql
   SELECT COUNT(*) FROM table_name;
   ```

- **Sum**:
   ```sql
   SELECT SUM(column_name) FROM table_name;
   ```

- **Average**:
   ```sql
   SELECT AVG(column_name) FROM table_name;
   ```

- **Min/Max**:
   ```sql
   SELECT MIN(column_name), MAX(column_name) FROM table_name;
   ```

---

### **11. Joins**
- **Inner Join**:
   ```sql
   SELECT column1, column2, ...
   FROM table1
   INNER JOIN table2
   ON table1.column = table2.column;
   ```

- **Left Join**:
   ```sql
   SELECT column1, column2, ...
   FROM table1
   LEFT JOIN table2
   ON table1.column = table2.column;
   ```

- **Right Join**:
   ```sql
   SELECT column1, column2, ...
   FROM table1
   RIGHT JOIN table2
   ON table1.column = table2.column;
   ```

- **Full Outer Join**:
   ```sql
   SELECT column1, column2, ...
   FROM table1
   FULL OUTER JOIN table2
   ON table1.column = table2.column;
   ```

---

### **12. Backup and Restore**
- **Backup a Database**:
   ```bash
   pg_dump dbname > backup_file.sql
   ```

- **Restore a Database**:
   ```bash
   psql dbname < backup_file.sql
   ```

---

These are essential SQL commands you will commonly use with PostgreSQL. Let me know if you need further explanations on any specific command!