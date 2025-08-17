# Main Categories of SQL Statements
1. **DDL** : Data Definition Language
2. **DML** : Data Manipulation Language
3. **DQL** : Data Query Language
4. **DCL** : Data Control Language
5. **TCL** : Transaction Control Language



## DDL – Data Definition Language
* `CREATE`
  * Database
  * Table
  * Index, View, Stored Procedure, Trigger
* `ALTER`
  * Add/modify/drop columns
  * Change datatype, constraints, table options
* `DROP`
  * Database, Table, View, Index
* `TRUNCATE` vs `DELETE`
* `RENAME`
* `SHOW` and `DESCRIBE`


## DML – Data Manipulation Language
* `INSERT`
  * Single row vs multiple rows
  * `INSERT IGNORE`, `INSERT ... ON DUPLICATE KEY UPDATE`
* `UPDATE`
  * With `WHERE`
  * With joins
* `DELETE`
  * With conditions
  * Performance considerations



## DQL – Data Query Language (SELECT)
* Basic `SELECT`
* `DISTINCT`
* `WHERE` clause (comparison, logical operators, pattern matching)
* `ORDER BY`, `LIMIT`
* **Aggregate functions** (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`)
* `GROUP BY` and `HAVING`
* **Joins**
  * Inner Join
  * Left Join / Right Join
  * Full Outer Join (workarounds in MySQL)
  * Cross Join
  * Self Join
* **Subqueries**
  * Scalar, Row, Table subqueries
  * Correlated subqueries
* **Set operations**
  * `UNION`, `UNION ALL`, `INTERSECT` (via workaround), `EXCEPT`
* Advanced clauses:
  * `CASE`, `IF`, `COALESCE`, `NULLIF`
  * Window Functions (`ROW_NUMBER`, `RANK`, `LEAD`, `LAG`)
  * CTE (`WITH`)


## DCL – Data Control Language
* `GRANT` – Assigning privileges
* `REVOKE` – Removing privileges
* `SHOW GRANTS`
* User management (`CREATE USER`, `DROP USER`, `ALTER USER`)



## TCL – Transaction Control Language
* Concept of transactions & ACID properties
* `START TRANSACTION` / `BEGIN`
* `COMMIT`
* `ROLLBACK`
* `SAVEPOINT` & `ROLLBACK TO SAVEPOINT`
* `SET AUTOCOMMIT`