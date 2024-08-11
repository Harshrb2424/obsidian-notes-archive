# EXP:06(A) Querying

## Operators

### ANY
The ANY operator returns true if any of the subquery values meet the condition.

### ALL
The ALL operator is used to select all tuples of the SELECT statement. It is also used to compare a value to every value in another value set or result from a subquery.

### SOME
The SOME operator compares a value to each value in all stored results from a query and evaluates to true if the result of an inner query contains at least one row.

## Syntax
```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator {ANY/ALL/SOME}
(SELECT column_name FROM table_name WHERE condition);
```

## Examples

### Table Creation and Data Insertion
```sql
mysql> CREATE TABLE t1 (cid INT PRIMARY KEY, Name VARCHAR(20));
mysql> INSERT INTO t1 VALUES (1, 'Rahul'), (2, 'Yash'), (3, 'Henry'), (4, 'Smith');

mysql> CREATE TABLE t2 (ID INT PRIMARY KEY, cid INT, date INT);
mysql> INSERT INTO t2 VALUES (1, 1, 2017), (2, 2, 2017), (3, 2, 2017), (4, 1, 2018), (5, 3, 2018);
```

### Queries

#### Using ALL
```sql
mysql> SELECT cid FROM t1 WHERE cid <> ALL (SELECT cid FROM t2);
+-----+
| cid |
+-----+
|  4  |
+-----+
```

#### Using ANY
```sql
mysql> SELECT cid FROM t1 WHERE cid <> ANY (SELECT cid FROM t2);
+-----+
| cid |
+-----+
|  1  |
|  2  |
|  3  |
|  4  |
+-----+
```

#### Using ANY (Equality)
```sql
mysql> SELECT cid FROM t1 WHERE cid = ANY (SELECT cid FROM t2);
+-----+
| cid |
+-----+
|  1  |
|  2  |
|  3  |
+-----+
```

#### Using SOME
```sql
mysql> SELECT cid FROM t1 WHERE cid = SOME (SELECT cid FROM t2);
+-----+
| cid |
+-----+
|  1  |
|  2  |
|  3  |
+-----+
```

#### Using IN
```sql
mysql> SELECT cid FROM t1 WHERE cid = IN (SELECT cid FROM t2);
+-----+
| cid |
+-----+
|  1  |
|  2  |
|  3  |
+-----+
```

## EXISTS / NOT EXISTS

The EXISTS condition in SQL is used to check whether the result of a correlated nested query is empty (contains no tuples) or not.

### Syntax
```sql
SELECT column_name(s) FROM table_name WHERE EXISTS
(SELECT column_name(s) FROM table_name WHERE condition);
```

### Examples

#### Using EXISTS
```sql
mysql> SELECT cid FROM t1 WHERE EXISTS (SELECT * FROM t2 WHERE t1.cid = t2.cid);
+-----+
| cid |
+-----+
|  1  |
|  2  |
|  3  |
+-----+
```

#### Using NOT EXISTS
```sql
mysql> SELECT cid FROM t1 WHERE NOT EXISTS (SELECT * FROM t2 WHERE t1.cid = t2.cid);
+-----+
| cid |
+-----+
|  4  |
+-----+
```

## UNION

The UNION operator is used to combine the result-set of two or more SELECT statements.

- Each SELECT statement within UNION must have the same number of columns.
- The columns must also have similar data types.
- The columns in each SELECT statement must also be in the same order.

## INTERSECT

The SQL INTERSECT clause/operator is used to combine two SELECT statements. But it returns only common rows returned by the two SELECT statements.

### Syntax
```sql
SELECT column_name(s) FROM table1
{UNION/INTERSECT}
SELECT column_name(s) FROM table2;
```

# EXP-6(B): Nested and Correlated Subqueries

## Nested Queries

Nested queries are a way to perform more complex queries by embedding one query within another. A nested query is a query that appears inside another query, and it helps retrieve data from multiple tables or apply conditions based on the results of another query.

### Example Tables

#### STUDENT
| S_ID | S_NAME | S_ADDRESS | S_PHONE     | S_AGE |
|------|--------|-----------|-------------|-------|
| S1   | RAM    | DELHI     | 9455123541  | 18    |
| S2   | RAMESH | GURGAON   | 9652431543  | 19    |
| S3   | SUJIT  | ROHTAK    | 9156253131  | 20    |
| S4   | SURESH | DELHI     | 9156768971  | 18    |

#### COURSE
| C_ID | C_NAME     |
|------|------------|
| C1   | DSA        |
| C2   | PROGRAMING |
| C3   | DBMS       |

#### STUDENT_COURSE
| S_ID | C_ID |
|------|------|
| S1   | C1   |
| S2   | C3   |
| S3   | C1   |
| S4   | C2   |
| S5   | C2   |

## Types of Nested Queries

### Independent Nested Queries

In independent nested queries, query execution starts from the innermost query to the outermost queries. The execution of the inner query is independent of the outer query, but the result of the inner query is used in the execution of the outer query. Various operators like IN, NOT IN, ANY, ALL, etc., are used.

### Example
```sql
SELECT StudentName
FROM Students
WHERE StudentID IN (
    SELECT StudentID
    FROM Grades
    WHERE Subject = 'Mathematics' AND Score > 90
);
```

### Co-related Nested Queries

In co-related nested queries, the output of the inner query depends on the row which is being currently executed in the outer query.

## Correlated Subqueries

Correlated subqueries are used for row-by-row processing. Each subquery is executed once for every row of the outer query. A correlated subquery is evaluated once for each row processed by the parent statement. The parent statement can be a SELECT, UPDATE, or DELETE statement.

### Correlated SELECT
```sql
SELECT column1, column2, ....
FROM table1 outer
WHERE column1 operator (
    SELECT column1, column2
    FROM table2
    WHERE expr1 = outer.expr2
);
```

### Correlated UPDATE
```sql
UPDATE table1 alias1
SET column = (
    SELECT expression 
    FROM table2 alias2
    WHERE alias1.column = alias2.column
);
```

### Correlated DELETE
```sql
DELETE FROM table1 alias1
WHERE column1 operator (
    SELECT expression
    FROM table2 alias2
    WHERE alias1.column = alias2.column
);
```

## Using the EXISTS Operator

The EXISTS operator tests for the existence of rows in the result set of the subquery. If a subquery row value is found, the condition is flagged TRUE and the search does not continue in the inner query. If it is not found, the condition is flagged FALSE and the search continues in the inner query.

### Example
```sql
SELECT employee_id, last_name, job_id, department_id
FROM employees outer
WHERE EXISTS (
    SELECT 'X'
    FROM employees
    WHERE manager_id = outer.employee_id
);
```
# EXP-07: Queries

## Group By

- The `GROUP BY` clause groups a set of rows into a set of summary rows by the values of columns or expressions.
- Generally, it is used with aggregate functions like `SUM`, `AVG`, `MAX`, `MIN`, and `COUNT`.

### Syntax
```sql
SELECT col1, col2, ..., aggregate_function(col)
FROM table_name
WHERE condition
GROUP BY col1, col2, ...
```

### HAVING Clause
- The `HAVING` clause is used to filter the groups returned by the `GROUP BY` clause.

### Syntax
```sql
SELECT col1, col2, ..., aggregate_function(col)
FROM table_name
WHERE condition
GROUP BY col1, col2, ...
HAVING condition
```

## Sample Tables

### Faculty
| Fid | fname | qualification | Deptid |
|-----|-------|----------------|--------|
| 1   | Adam  | B.Tech         | 1      |
| 2   | Milan | M.Tech         | 1      |
| 3   | Victor| M.Tech         | 1      |
| 4   | Peter | Phd            | 2      |
| 5   | Ricky | Phd            | 3      |
| 6   | Alice | M.Tech         | 2      |
| 7   | Henry | Phd            | 5      |

### Student
| Sid | Sname | Branch | marks |
|-----|-------|--------|-------|
| 1   | Lenin | IT     | 75    |
| 2   | Martin| IT     | 90    |
| 3   | Sam   | CSE    | 92    |
| 4   | Alice | CSE    | 45    |
| 5   | Shivam| ECE    | 56    |
| 6   | Adam  | ECE    | 78    |
| 7   | Peter | IT     | 82    |
| 8   | John  | NULL   | 89    |

### Department
| Deptid | dname   |
|--------|---------|
| 1      | IT      |
| 2      | CSE     |
| 3      | ECE     |
| 4      | EEE     |
| 5      | ICE     |
| 6      | CIVIL   |
| 7      | Maths   |
| 8      | English |

## Views

- A view is a virtual table based on the result-set of an SQL statement.
- A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

### Syntax
```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Examples

1. **Create a view that contains records of only IT and CSE students**
    ```sql
    CREATE VIEW view1 AS
    SELECT * FROM student
    WHERE branch IN ('IT', 'CSE');
    ```

    #### view1 Result:
| Sid | Sname  | Branch | marks |
|-----|--------|--------|-------|
| 1   | Lenin  | IT     | 75    |
| 2   | Martin | IT     | 90    |
| 3   | Sam    | CSE    | 92    |
| 4   | Alice  | CSE    | 45    |
| 7   | Peter  | IT     | 82    |

2. **Create a view that contains records where marks are greater than the average marks**
    ```sql
    CREATE VIEW view3 AS
    SELECT * FROM student
    WHERE marks > (SELECT AVG(marks) FROM student);
    ```

    #### view3 Result:

| Sid | Sname  | Branch | marks |
|-----|--------|--------|-------|
| 2   | Martin | IT     | 90    |
| 3   | Sam    | CSE    | 92    |
| 6   | Adam   | ECE    | 78    |
| 7   | Peter  | IT     | 82    |
| 8   | John   | NULL   | 89    |

3. **Create a view that contains records with Deptid 1 and 2**
    ```sql
    CREATE VIEW view4 AS
    SELECT * FROM faculty
    WHERE deptid IN (1, 2);
    ```

    #### view4 Result:
| Fid | fname  | qualification | Deptid |
|-----|--------|---------------|--------|
| 1   | Adam   | B.Tech        | 1      |
| 2   | Milan  | M.Tech        | 1      |
| 3   | Victor | M.Tech        | 1      |
| 4   | Peter  | Phd           | 2      |
| 6   | Alice  | M.Tech        | 2      |

4. **Create a view with a check option**
    ```sql
    CREATE VIEW view6 AS
    SELECT * FROM department
    WHERE deptid = 1
    WITH CHECK OPTION;
    ```

    #### Insert into view6
    ```sql
    INSERT INTO view6 VALUES (11, 'Biology');
    ```

    #### O/P: Check Option Failed

# EXP-08: Triggers

A trigger is a PL/SQL block structure which is fired when a DML statement like `INSERT`, `DELETE`, or `UPDATE` is executed on a database table. A trigger is triggered automatically when an associated DML statement is executed.

## Syntax

```sql
CREATE TRIGGER trigger_name
[BEFORE | AFTER] {INSERT | UPDATE | DELETE}
ON table_name
FOR EACH ROW
BEGIN
    -- trigger logic
END;
```

## Example-01

### Create `sales` table and insert a record

```sql
CREATE TABLE sales (
    sid INT PRIMARY KEY,
    itemid INT,
    qtysold INT,
    price INT,
    total INT
);

INSERT INTO sales VALUES (101, 8, 10, 90, 0);

SELECT * FROM sales;
```

#### Output

| sid | itemid | qtysold | price | total |
|-----|--------|---------|-------|-------|
| 101 | 8      | 10      | 90    | 0     |

### Create and execute trigger `t1` before insert

```sql
DELIMITER //
CREATE TRIGGER t1 BEFORE INSERT
ON sales
FOR EACH ROW
BEGIN
    SET NEW.total = NEW.qtysold * NEW.price;
END;
//
DELIMITER ;
```

### Insert another record into `sales`

```sql
INSERT INTO sales VALUES (102, 9, 10, 180, 0);

SELECT * FROM sales;
```

#### Output

| sid | itemid | qtysold | price | total |
|-----|--------|---------|-------|-------|
| 101 | 8      | 10      | 90    | 0     |
| 102 | 9      | 10      | 180   | 1800  |

### Drop trigger `t1`

```sql
DROP TRIGGER t1;
```

## Example-02

### Create `item` table and insert a record

```sql
CREATE TABLE item (
    itemid INT PRIMARY KEY,
    qoh INT
);

INSERT INTO item VALUES (14, 59);

SELECT * FROM item;
```

#### Output

| itemid | qoh |
|--------|-----|
| 14     | 59  |

### Create and execute trigger `t1` before insert

```sql
DELIMITER //
CREATE TRIGGER t1 BEFORE INSERT
ON sales
FOR EACH ROW
BEGIN
    SET NEW.total = NEW.qtysold * NEW.price;
    UPDATE item
    SET qoh = qoh - NEW.qtysold
    WHERE item.itemid = NEW.itemid;
END;
//
DELIMITER ;
```

### Insert another record into `sales`

```sql
INSERT INTO sales VALUES (103, 14, 15, 180, 0);

SELECT * FROM item;
```

#### Output

| itemid | qoh |
|--------|-----|
| 14     | 44  |

### Select records from `sales`

```sql
SELECT * FROM sales;
```

#### Output

| sid | itemid | qtysold | price | total |
|-----|--------|---------|-------|-------|
| 101 | 8      | 10      | 90    | 0     |
| 102 | 9      | 10      | 180   | 1800  |
| 103 | 14     | 15      | 180   | 2700  |

## Example-03

### Create `student` table

```sql
CREATE TABLE student (
    sid INT PRIMARY KEY,
    name VARCHAR(20),
    s1 INT,
    s2 INT,
    s3 INT,
    total INT
);
```

### Create and execute trigger `t3` before insert

```sql
DELIMITER //
CREATE TRIGGER t3 BEFORE INSERT
ON student
FOR EACH ROW
BEGIN
    SET NEW.total = NEW.s1 + NEW.s2 + NEW.s3;
END;
//
DELIMITER ;
```

### Insert a record into `student`

```sql
INSERT INTO student VALUES (1, 'Harsh', 20, 20, 20, 0);

SELECT * FROM student;
```

#### Output

| sid | name  | s1  | s2  | s3  | total |
| --- | ----- | --- | --- | --- | ----- |
| 1   | Harsh | 20  | 20  | 20  | 60    |
# EXP-09: Procedures

- A procedure or function is a group or set of SQL and PL/SQL statements that perform a specific task.
- A procedure and function is a named PL/SQL Block which is similar.
- A procedure has a header and a body. The header consists of the name of the procedure and the parameters or variables passed to the procedure.
- The body consists of a declaration section, execution section, and exception section similar to a general PL/SQL Block. A procedure is similar to an anonymous PL/SQL Block but it is named for repeated usage.
- We can pass parameters to procedures in three ways:

### Parameters Description

| Parameters | Description |
|------------|-------------|
| IN type    | These types of parameters are used to send values to stored procedures. |
| OUT type   | These types of parameters are used to get values from stored procedures. This is similar to a return type in functions. |
| INOUT type | These types of parameters are used to send values and get values from stored procedures. |

A procedure may or may not return any value.

## Syntax

```sql
CREATE [OR REPLACE] PROCEDURE procedure_name(<Argument> {IN, OUT, INOUT} <Datatype>, …)
IS
    Declaration section <variable, constant>;
BEGIN
    Execution section
EXCEPTION
    Exception section
END;
```

### Example

#### Create `item` table and insert records

```sql
CREATE TABLE item (
    itemid INT PRIMARY KEY,
    idesc VARCHAR(20),
    qoh INT,
    price INT
);

INSERT INTO item VALUES 
(7, 'pen', 60, 300),
(8, 'Note', 59, 100),
(9, 'pencil', 59, 100),
(10, 'Book', 57, 100),
(11, 'toy', 50, NULL);
```

### Example-01: Display Items

```sql
DELIMITER /

CREATE PROCEDURE disp_item()
BEGIN
    SELECT * FROM item;
END;
/
DELIMITER ;
CALL disp_item();
```

#### Output

| itemid | idesc  | qoh | price |
|--------|--------|-----|-------|
| 7      | pen    | 60  | 300   |
| 8      | Note   | 59  | 100   |
| 9      | pencil | 59  | 100   |
| 10     | Book   | 57  | 100   |
| 11     | toy    | 50  | NULL  |

### Example-02: Find Item by ID

```sql
DELIMITER /
CREATE PROCEDURE find_item(IN id INT)
BEGIN
    SELECT * FROM item WHERE itemid = id;
END;
/
DELIMITER ;
CALL find_item(1); -- Empty set

CALL find_item(10);
```

#### Output

| itemid | idesc | qoh | price |
|--------|-------|-----|-------|
| 10     | Book  | 57  | 100   |

### Example-03: Local Variables

```sql
DELIMITER //
CREATE PROCEDURE Local_Variables()
BEGIN
    DECLARE a INT DEFAULT 10;
    DECLARE b, c INT;

    SET a = a + 100;
    SET b = 2;
    SET c = a + b;

    BEGIN
        DECLARE c INT;
        SET c = 5;
        
        SELECT a, b, c;
    END;

    SELECT a, b, c;
END;
//
DELIMITER ;
CALL Local_Variables();
```

#### Output

First SELECT statement inside the nested block:

| a   | b | c |
|-----|---|---|
| 110 | 2 | 5 |

Second SELECT statement in the main block:

| a   | b | c   |
|-----|---|-----|
| 110 | 2 | 112 |

# EXP-10: Usage of Cursors

In MySQL, cursors can also be created. The following are the steps for creating a cursor.

## Steps for Creating a Cursor

### 1. Declare Cursor

A cursor is a select statement, defined in the declaration section in MySQL.

**Syntax:**
```sql
DECLARE cursor_name CURSOR FOR select_statement;
```

**Parameters:**
- `cursor_name`: name of the cursor
- `select_statement`: select query associated with the cursor

### 2. Open Cursor

After declaring the cursor, the next step is to open the cursor using the open statement.

**Syntax:**
```sql
OPEN cursor_name;
```

**Parameter:**
- `cursor_name`: name of the cursor which is already declared

### 3. Fetch Cursor

After declaring and opening the cursor, the next step is to fetch the cursor. It is used to fetch the row or the column.

**Syntax:**
```sql
FETCH [NEXT [FROM]] cursor_name INTO variable_list;
```

**Parameters:**
- `cursor_name`: name of the cursor
- `variable_list`: variables, comma-separated, etc. is stored in a cursor for the result set

### 4. Close Cursor

The final step is to close the cursor.

**Syntax:**
```sql
CLOSE cursor_name;
```

**Parameter:**
- `cursor_name`: name of the cursor

## Example for the Cursor

### Step 1: Open the Database and Table

```sql
CREATE TABLE table1 (
    id INT(5),
    name VARCHAR(15),
    class VARCHAR(10)
);

INSERT INTO table1 VALUES 
(1, 'shristee', 'MCA'),
(2, 'Ajay', 'BCA'),
(3, 'Shweta', 'MCA'),
(4, 'Dolly', 'BCA');
```

### Step 2: Use the Database

```sql
USE test1;
```

### Step 3: Select Data from the Table

```sql
SELECT * FROM table1;
```

#### Output

| id  | name     | class |
| --- | -------- | ----- |
| 1   | Shristee | MCA   |
| 2   | Ajay     | BCA   |
| 3   | Shweta   | MCA   |


### Step 4: Using Cursor

```sql
DELIMITER //

CREATE PROCEDURE cursor_example()
BEGIN
    DECLARE v_id INT;
    DECLARE v_name VARCHAR(15);
    DECLARE v_class VARCHAR(10);
    
    DECLARE done INT DEFAULT FALSE;
    
    DECLARE cursor1 CURSOR FOR 
    SELECT id, name, class 
    FROM table1;
    
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    
    OPEN cursor1;
    
    read_loop: LOOP
        FETCH cursor1 INTO v_id, v_name, v_class;
        IF done THEN
            LEAVE read_loop;
        END IF;
        
        SELECT v_id, v_name, v_class;
    END LOOP;
    CLOSE cursor1;
END
//

DELIMITER ;

```

#### Output

| v_id | v_name   | v_class |
| ---- | -------- | ------- |
| 1    | Shristee | MCA     |

| v_id | v_name | v_class |
| ---- | ------ | ------- |
| 2    | Ajay   | BCA     |

| v_id | v_name | v_class |
| ---- | ------ | ------- |
| 3    | Shweta | MCA     |

| v_id | v_name | v_class |
| ---- | ------ | ------- |
| 4    | Dolly  | BCA     |
