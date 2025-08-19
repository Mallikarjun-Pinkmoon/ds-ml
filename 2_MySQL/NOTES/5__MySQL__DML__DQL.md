1. # Data Query Language (DML)
2. # Data Manipulation Language (DML)

* `SELECT`
* `INSERT`
* `UPDATE`
* `DELETE`


<br/>
<br/>
<br/>

# 1. `SELECT` – Retrieve Data

**Basic Structure:**

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
GROUP BY column
HAVING condition
ORDER BY column ASC|DESC
LIMIT n OFFSET m;
```

**Examples:**

```sql
-- Example 1: Select all columns
SELECT * FROM Employees;

-- Example 2: Select specific columns
SELECT emp_id, name, salary FROM Employees;

-- Example 3: With condition
SELECT name, salary FROM Employees
WHERE salary > 50000;

-- Example 4: Sorting
SELECT name, salary FROM Employees
ORDER BY salary DESC;

-- Example 5: Aggregates with GROUP BY
SELECT dept_id, AVG(salary) AS avg_salary
FROM Employees
GROUP BY dept_id
HAVING AVG(salary) > 60000;

-- Example 6: LIMIT (MySQL/Postgres)
SELECT * FROM Employees LIMIT 5 OFFSET 10;
```

<br/>
<br/>
<br/>

# 2. `INSERT` – Add New Records

**Basic Structure:**

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

**Examples:**

```sql
-- Example 1: Insert all values
INSERT INTO Students (id, name, age)
VALUES (1, 'Alice', 20);

-- Example 2: Insert only selected columns
INSERT INTO Students (name, age)
VALUES ('Bob', 21);

-- Example 3: Insert multiple rows
INSERT INTO Students (id, name, age)
VALUES 
(2, 'Charlie', 22),
(3, 'David', 23);

-- Example 4: Insert from another table
INSERT INTO GraduateStudents (id, name)
SELECT id, name FROM Students WHERE age > 21;
```

<br/>
<br/>
<br/>

## 3. `UPDATE` – Modify Existing Records

**Basic Structure:**

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

**Examples:**

```sql
-- Example 1: Update single column
UPDATE Employees
SET salary = 60000
WHERE emp_id = 101;

-- Example 2: Update multiple columns
UPDATE Employees
SET salary = 70000, dept_id = 2
WHERE emp_id = 102;

-- Example 3: Update without WHERE (⚠ updates all rows!)
UPDATE Employees
SET dept_id = 1;

-- Example 4: Update with subquery
UPDATE Employees
SET salary = salary * 1.1
WHERE dept_id = (SELECT dept_id FROM Departments WHERE dept_name = 'HR');
```

<br/>
<br/>
<br/>

## 4. `DELETE` – Remove Records

**Basic Structure:**

```sql
DELETE FROM table_name
WHERE condition;
```

**Examples:**

```sql
-- Example 1: Delete specific record
DELETE FROM Students
WHERE id = 1;

-- Example 2: Delete with condition
DELETE FROM Employees
WHERE salary < 30000;

-- Example 3: Delete all rows (⚠)
DELETE FROM Students;

-- Example 4: Delete using subquery
DELETE FROM Employees
WHERE dept_id = (SELECT dept_id FROM Departments WHERE dept_name = 'ClosedDept');
```

<br/>
<br/>
<br/>

* **SELECT** → retrieve data
* **INSERT** → add data
* **UPDATE** → modify data
* **DELETE** → remove data

