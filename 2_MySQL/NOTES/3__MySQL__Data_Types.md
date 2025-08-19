# "DATA TYPES" IN MySQL

## NEUMERIC Data Types
1. `INT` / `INTEGER` (8 Bytes)
2. `TINYINT` (1 Byte)
3. `SMALLINT` (2 Byte)
4. `FLOAT` (4 Bytes) : 7 Decimal Places
5. `DOUBLE` (8 Bytes) : 15 Decimal Places
6. `DECIMAL` (M, D) 
   1. M - Total No of Digits
   2. D - Digits After Decimal point
   3. Eg.
      1. M=5, D=3 >>> 34.778
7. `MEDIUMINT` (4 Bytes)
8. `BIGINT` (16 / 32 / 64 Bytes)


## TEXT
1. `CHAR` (1 Byte)
2. `VARCHAR(N)` (Fixed Length)
3. `TEXT` (Variably Large)


## OTHER
1. `SET` (Can have Multiple Options)
   1. `SET("JAVA", "PY", "C", "C++")`
2. `ENUME` (Only Single Option Allowed)
   1. `ENUM("A", "B", "C")`
3. `BLOB` (File Storage)
4. ....

<br/>
<br/>
<br/>


# 1. Numeric (Exact & Approximate)

1. TINY
2. SMALL
3. MEDIUM
4. INT
5. BIG
<!---------------->
1. DECIMAL
2. FLOAT
3. DOUBLE

| Keyword                             | Storage (Approx) | Description                                                          |
| ----------------------------------- | ---------------- | -------------------------------------------------------------------- |
| **`TINYINT`**                       | 1 Byte           | Very small integer (range: -128 to 127 or 0–255 if UNSIGNED).        |
| **`SMALLINT`**                      | 2 Bytes          | Small integer (range: -32,768 to 32,767).                            |
| **`MEDIUMINT`**                     | 3 Bytes          | Medium integer (range: -8M to 8M).                                   |
| **`INT` / `INTEGER`**               | 4 Bytes          | Standard integer (range: -2.1B to 2.1B).                             |
| **`BIGINT`**                        | 8 Bytes          | Very large integer (range: -9 quintillion to 9 quintillion).         |
| **`DECIMAL(M,D)` / `NUMERIC(M,D)`** | Variable         | User-defined precision. <br> Example: `DECIMAL(5,2)` → max `999.99`. |
| **`FLOAT(p)`**                      | 4 Bytes          | Approximate decimal (single precision, \~7 digits).                  |
| **`DOUBLE` / `REAL`**               | 8 Bytes          | Approximate decimal (double precision, \~15 digits).                 |
| **`BOOLEAN` / `BOOL`**              | 1 Byte           | Logical true/false values.                                           |

<br/>
<br/>
<br/>


## 📝 2. Character & String (Text Types)

| Keyword                       | Storage            | Description                                                                               |
| ----------------------------- | ------------------ | ----------------------------------------------------------------------------------------- |
| **`CHAR(n)`**                 | Fixed (0–255)      | Always reserves *n* Bytes, padded with spaces. Good for codes like `CHAR(2)` = "US".      |
| **`VARCHAR(n)`**              | Variable (0–65535) | Stores only actual length + 1/2 Bytes overhead. Efficient for text that varies in length. |
| **`TEXT`**                    | 64 KB              | Large variable-length text.                                                               |
| **`TINYTEXT`**                | 255 chars          | Small text storage.                                                                       |
| **`MEDIUMTEXT`**              | 16 MB              | Medium-sized text.                                                                        |
| **`LONGTEXT`**                | 4 GB               | Very large text storage (articles, documents).                                            |
| **`ENUM('val1','val2',...)`** | 1–2 Bytes          | Single value chosen from a predefined list.                                               |
| **`SET('val1','val2',...)`**  | 1–8 Bytes          | Multiple values allowed from a predefined list.                                           |

<br/>
<br/>
<br/>


## 3. Date & Time

| Keyword         | Storage | Description                                 |
| --------------- | ------- | ------------------------------------------- |
| **`DATE`**      | 3 Bytes | Stores only date in format `YYYY-MM-DD`.    |
| **`DATETIME`**  | 8 Bytes | Stores date & time (`YYYY-MM-DD HH:MM:SS`). |
| **`TIMESTAMP`** | 4 Bytes | Stores UTC timestamp (1970–2038 range).     |
| **`TIME`**      | 3 Bytes | Stores only time (`HH:MM:SS`).              |
| **`YEAR`**      | 1 Byte  | Stores year (`YYYY` format).                |

<br/>
<br/>
<br/>


## 4. Binary & Other Special Types

| Keyword             | Storage   | Description                                          |
| ------------------- | --------- | ---------------------------------------------------- |
| **`BLOB`**          | 64 KB     | Binary Large Object (images, files, audio).          |
| **`TINYBLOB`**      | 255 Bytes | Small binary storage.                                |
| **`MEDIUMBLOB`**    | 16 MB     | Medium binary storage.                               |
| **`LONGBLOB`**      | 4 GB      | Very large binary storage.                           |
| **`JSON`**          | Variable  | Stores JSON objects (MySQL, PostgreSQL, SQL Server). |
| **`XML`**           | Variable  | Stores XML data (SQL Server, Oracle).                |
| **`UUID` / `GUID`** | 16 Bytes  | Stores unique identifiers.                           |
| **`GEOMETRY`**      | Variable  | Stores spatial data (points, lines, polygons).       |

<br/>
<br/>
<br/>
