- 001 SQL Commands_ CREATE Table and INSERT Data
    
    - In database you mostly do CRUD (Create Read Update Destroy).
    - Create with `CREATE TABLE table_name ()` , `NOT NULL` to make the item necessary to be created. `PRIMARY KEY (id)` to make it unique.
    
    ```sql
    CREATE TABLE table_name (
        column1 datatype,
        id INT NOT NULL,
    		name STRING,
        price MONEY,
    	  PRIMARY KEY (id)
    )
    ```
    
    - Add Data (INSERT data) with `INSERT INTO table_name () VALUES ()`
    
    ```sql
    INSERT INTO table_name (column1, column2, column3, ...)
    VALUES (value1, value2, value3, ...)
    //or (to add all data)//
    INSERT INTO table_name
    VALUES (value1, value2, value3, ...);
    ```
    
- 002 SQL Commands_ READ, SELECT, and WHERE
    
    - `SELECT * FROM table_name;`
        
        - - → all the data
        - u can use column name `SELECT name, id FROM table_name;`
    - `SELECT * FROM *table_name* WHERE *condition`*
        
        - WHERE _condition → WHERE id=2_
        
        ```sql
        SELECT column1, column2, ...
        FROM table_name
        WHERE condition
        ```
        
- 003 Updating Single Values and Adding Columns in SQL UPDATE ALTER
    
    - UPDATE add details in existing column
    
    ```sql
    UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE condition;
    ```
    
    - Add column’s with ALTER
    
    ```sql
    ALTER TABLE table_name
    ADD column_name datatype;
    ```
    
- 004 SQL Commands_ DELETE
    
    ```sql
    DELETE FROM table_name WHERE condition;
    ```
    
- 005 Understanding SQL Relationships, FOREIGN KEY and INNER JOIN
    
    ```sql
    //while creating table (CREATE TABLE table_name)//
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Person_table (PersonID)
    ```
    
    - `SELECT`the appropriate columns
    - `ON` condition similar in the 2 tables
    
    ```sql
    SELECT column_name(s)
    FROM table1
    INNER JOIN table2
    ON table1.column_name = table2.column_name;
    ```
