# Constraints / Restrictions 

1. `NOT NULL` : Dosent Allow Null / Empty Values
2. `DEFAULT` : Sets Default Value When Not Mentioned
3. `UNIQUE` : Makes Sure the Values are Not Repeated
4. `PRIMARY KEY` : UNIQUE + NOT NULL + INDEX
5. `AUTO_INCREMENT` : Automatically increments a integer
6. `FOREIGN KEY` : References columns in other tables
   1. References Other Column of **Same** or **Different** Tables
   2. Linking Records
   3. Eg.
      1. Followers / Following
         1. user1 --- follows ---- user2
         2. user1 --- follows ---- user3
7. `CHECK` : Manual Constraints
   1. `CHECK  ((age > 16) AND (age < 20))`
8. `ENUM / SET` : Allows only specified Values

<br />
<br />
<br />

## 1. `NOT NULL`

Prevents a column from storing `NULL` values.

**Structure:**

```sql
CREATE TABLE table_name (
    column_name datatype NOT NULL
);
```

**Examples:**

```sql
-- Example 1: Ensuring name cannot be NULL
CREATE TABLE Students (
    student_id INT,
    name VARCHAR(50) NOT NULL
);

-- Example 2: Insert will fail if name is NULL
INSERT INTO Students (student_id, name) VALUES (1, NULL); -- ❌ Error
```

<br />
<br />
<br />

## 2. `DEFAULT`

Assigns a value automatically if not provided.

**Structure:**

```sql
CREATE TABLE table_name (
    column_name datatype DEFAULT default_value
);
```

**Examples:**

```sql
-- Example 1: Default status is 'active'
CREATE TABLE Users (
    user_id INT,
    status VARCHAR(10) DEFAULT 'active'
);

INSERT INTO Users (user_id) VALUES (1);
-- status will be 'active'

-- Example 2: Default timestamp
CREATE TABLE Orders (
    order_id INT,
    order_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

<br />
<br />
<br />

## 3. `UNIQUE`

Ensures all values in a column are different.

**Structure:**

```sql
CREATE TABLE table_name (
    column_name datatype UNIQUE
);
```

**Examples:**

```sql
-- Example 1: Emails must be unique
CREATE TABLE Employees (
    emp_id INT,
    email VARCHAR(100) UNIQUE
);

-- Example 2: Composite UNIQUE (combination must be unique)
CREATE TABLE Enrollment (
    student_id INT,
    course_id INT,
    UNIQUE (student_id, course_id)
);
```

<br />
<br />
<br />

## 4. `PRIMARY KEY`

A combination of `NOT NULL` + `UNIQUE` + automatically indexed.

**Structure:**

```sql
CREATE TABLE table_name (
    column_name datatype PRIMARY KEY
);
```

**Examples:**

```sql
-- Example 1: Single column primary key
CREATE TABLE Departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50)
);

-- Example 2: Composite primary key
CREATE TABLE StudentCourses (
    student_id INT,
    course_id INT,
    PRIMARY KEY (student_id, course_id)
);
```

<br />
<br />
<br />

## 5. `AUTO_INCREMENT` (MySQL)

Automatically generates sequential numbers.

**Structure (MySQL):**

```sql
CREATE TABLE table_name (
    id INT AUTO_INCREMENT PRIMARY KEY
);
```

**Examples:**

```sql
-- Example 1: Auto increment ID
CREATE TABLE Products (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100)
);

-- Example 2: PostgreSQL
CREATE TABLE Customers (
    customer_id SERIAL PRIMARY KEY,
    name VARCHAR(50)
);
```

<br />
<br />
<br />

## 6. `FOREIGN KEY`

Links a column to another table’s column.

**Structure:**

```sql
CREATE TABLE child_table (
    column_name datatype,
    FOREIGN KEY (column_name) REFERENCES parent_table(parent_column)
);
```

**Examples:**

```sql
-- Example 1: Foreign key reference
CREATE TABLE Authors (
    author_id INT PRIMARY KEY,
    name VARCHAR(50)
);

CREATE TABLE Books (
    book_id INT PRIMARY KEY,
    title VARCHAR(100),
    author_id INT,
    FOREIGN KEY (author_id) REFERENCES Authors(author_id)
);

-- Example 2: Followers system
CREATE TABLE Followers (
    follower_id INT,
    following_id INT,
    FOREIGN KEY (follower_id) REFERENCES Users(user_id),
    FOREIGN KEY (following_id) REFERENCES Users(user_id)
);
```

<br />
<br />
<br />

## 7. `CHECK`

Adds conditions for values.

**Structure:**

```sql
CREATE TABLE table_name (
    column_name datatype CHECK (condition)
);
```

**Examples:**

```sql
-- Example 1: Age must be greater than 16
CREATE TABLE Teenagers (
    teen_id INT,
    age INT CHECK (age >= 13 AND age <= 19)
);

-- Example 2: Salary must be positive
CREATE TABLE Staff (
    staff_id INT,
    salary DECIMAL(10,2) CHECK (salary > 0)
);
```

<br />
<br />
<br />

## 8. `ENUM / SET` (MySQL specific)

Restricts values to a defined list.

**Structure:**

```sql
CREATE TABLE table_name (
    column_name ENUM('value1','value2','value3')
);
```

**Examples:**

```sql
-- Example 1: ENUM for gender
CREATE TABLE People (
    person_id INT,
    gender ENUM('Male','Female','Other')
);

-- Example 2: SET (multiple allowed)
CREATE TABLE UserPreferences (
    user_id INT,
    hobbies SET('Music','Sports','Travel','Reading')
);
```
