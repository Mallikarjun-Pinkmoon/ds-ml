# DDL (Data Definition Language) in MySQL

1. define and manage database structures 
2. Databases, Tables, Indexes, Views, etc.

## Main DDL Statements:

* `CREATE`
* `ALTER`
* `DROP`
* `TRUNCATE`
* `RENAME`
* `SHOW` / `DESCRIBE`

<br />
<br />

# 1. **CREATE**

### Purpose: Create databases, tables, indexes, views, procedures, triggers, etc.

### 1.1 Create Database

```sql
-- Create a new database
CREATE DATABASE company;

-- Create with character set and collation
CREATE DATABASE school
CHARACTER SET utf8mb4
COLLATE utf8mb4_unicode_ci;
```

📌 Notes:

* Use `SHOW DATABASES;` to verify.
* Default character set = `utf8mb4`.

---

### 1.2 Create Table

```sql
-- Basic table
CREATE TABLE employees (
    emp_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    department VARCHAR(50),
    salary DECIMAL(10,2) DEFAULT 0.00,
    hire_date DATE
);

-- Table with constraints
CREATE TABLE projects (
    project_id INT PRIMARY KEY,
    project_name VARCHAR(100) UNIQUE,
    start_date DATE NOT NULL,
    end_date DATE,
    emp_id INT,
    FOREIGN KEY (emp_id) REFERENCES employees(emp_id)
);
```

📌 Key constraints:

* `PRIMARY KEY` → unique + not null
* `FOREIGN KEY` → maintains referential integrity
* `UNIQUE` → unique values allowed
* `NOT NULL` → cannot be null
* `DEFAULT` → default value

---

### 1.3 Create Index

```sql
-- Create single column index
CREATE INDEX idx_emp_name ON employees(name);

-- Create multi-column index
CREATE INDEX idx_emp_dept_salary ON employees(department, salary);
```

📌 Index improves search performance but slows down inserts/updates.

---

### 1.4 Create View

```sql
-- Create a view
CREATE VIEW high_salary_employees AS
SELECT name, department, salary
FROM employees
WHERE salary > 50000;

-- Query the view
SELECT * FROM high_salary_employees;
```

📌 Views simplify queries and improve readability.

---

### 1.5 Create Temporary Table

```sql
CREATE TEMPORARY TABLE temp_sales (
    product_id INT,
    sales_amount DECIMAL(10,2)
);
```

📌 Temporary tables exist only in the session.

<br />
<br />
<br />

## 2. **ALTER**

### Purpose: Modify existing database objects.

### 2.1 Alter Table – Add Column

```sql
ALTER TABLE employees
ADD COLUMN email VARCHAR(100);
```

### 2.2 Alter Table – Modify Column

```sql
ALTER TABLE employees
MODIFY COLUMN department VARCHAR(100) NOT NULL;
```

### 2.3 Alter Table – Rename Column

```sql
ALTER TABLE employees
CHANGE COLUMN name full_name VARCHAR(150);
```

### 2.4 Alter Table – Drop Column

```sql
ALTER TABLE employees
DROP COLUMN email;
```

### 2.5 Alter Table – Add Constraint

```sql
ALTER TABLE employees
ADD CONSTRAINT unique_name UNIQUE (full_name);
```

### 2.6 Rename Table

```sql
ALTER TABLE employees RENAME TO staff;
```

<br />
<br />
<br />

## 3. **DROP**

### Purpose: Permanently delete database objects.

### 3.1 Drop Database

```sql
DROP DATABASE company;
```

### 3.2 Drop Table

```sql
DROP TABLE employees;
```

### 3.3 Drop Index

```sql
DROP INDEX idx_emp_name ON employees;
```

### 3.4 Drop View

```sql
DROP VIEW high_salary_employees;
```

⚠️ **Irreversible! Data is permanently lost.**

<br />
<br />
<br />

## 4. **TRUNCATE**

### Purpose: Remove all rows from a table (faster than `DELETE`).

```sql
TRUNCATE TABLE employees;
```

📌 Notes:

* Resets `AUTO_INCREMENT`.
* Cannot use `WHERE` clause.
* Faster than `DELETE` because it doesn’t log row-by-row deletion.

<br />
<br />
<br />

## 5. **RENAME**

### Rename Table

```sql
RENAME TABLE staff TO employees_data;
```

<br />
<br />
<br />

## 6. **SHOW / DESCRIBE**

### Purpose: Retrieve schema metadata.

```sql
-- Show all databases
SHOW DATABASES;

-- Show all tables in current DB
SHOW TABLES;

-- Show table structure
DESCRIBE employees;

-- Detailed table schema
SHOW CREATE TABLE employees;
```

<br />
<br />
<br />


# DDL Statements

| Statement  | Purpose          |
| ---------- | ---------------- |
| `CREATE`   | Create object    |
| `ALTER`    | Modify object    |
| `DROP`     | Delete object    |
| `TRUNCATE` | Remove all rows  |
| `RENAME`   | Rename object    |
| `SHOW`     | Display metadata |

# Naming Conventions
1. UpperPascalCase : Database, Table Names
2. lowerPascalCase : columns, index, functions and other Names
3. snake_case : columns, index, functions and other Names

# key Important Things when Building a Table
1. Column Data Types
2. Column Constraints

# Structure of SQL
1. Statements (Every Statement SHould end with a Semi-Colan)
2. Clauses (Each State Can Contain One or More Clauses)
3. Commas will used to seperate argumenst of a clause or command
4. Semicoln is used to seperate Commands

