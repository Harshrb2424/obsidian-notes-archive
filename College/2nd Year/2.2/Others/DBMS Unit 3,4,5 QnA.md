# Unit 3
### 1. Explain DDL, DML, and TCL commands with example Queries.

**DDL (Data Definition Language):**
DDL commands are used to define or alter the structure of the database objects like tables, schemas, indexes, etc. 

- **CREATE**: Used to create a new table, schema, index, or other database objects.
  ```sql
  CREATE TABLE Students (
      StudentID int,
      Name varchar(255),
      Age int,
      Grade char(1)
  );
  ```

- **ALTER**: Used to modify an existing database object.
  ```sql
  ALTER TABLE Students
  ADD COLUMN Email varchar(255);
  ```

- **DROP**: Used to delete a database object.
  ```sql
  DROP TABLE Students;
  ```

- **TRUNCATE**: Used to remove all records from a table, but not the table itself.
  ```sql
  TRUNCATE TABLE Students;
  ```

**DML (Data Manipulation Language):**
DML commands are used to manipulate the data stored in the database.

- **INSERT**: Used to add new records to a table.
  ```sql
  INSERT INTO Students (StudentID, Name, Age, Grade)
  VALUES (1, 'John Doe', 20, 'A');
  ```

- **UPDATE**: Used to modify existing records in a table.
  ```sql
  UPDATE Students
  SET Age = 21
  WHERE StudentID = 1;
  ```

- **DELETE**: Used to remove records from a table.
  ```sql
  DELETE FROM Students
  WHERE StudentID = 1;
  ```

- **SELECT**: Used to retrieve records from one or more tables.
  ```sql
  SELECT * FROM Students;
  ```

**TCL (Transaction Control Language):**
TCL commands are used to manage transactions in the database. Transactions ensure that a group of SQL commands are executed as a single unit.

- **COMMIT**: Saves all changes made in the current transaction.
  ```sql
  COMMIT;
  ```

- **ROLLBACK**: Undoes all changes made in the current transaction.
  ```sql
  ROLLBACK;
  ```

- **SAVEPOINT**: Sets a savepoint within a transaction.
  ```sql
  SAVEPOINT Savepoint1;
  ```

- **RELEASE SAVEPOINT**: Deletes a savepoint.
  ```sql
  RELEASE SAVEPOINT Savepoint1;
  ```

- **SET TRANSACTION**: Sets the characteristics of the current transaction.
  ```sql
  SET TRANSACTION READ ONLY;
  ```

### 2. Explain about Aggregate Functions in DBMS with example queries.

Aggregate functions perform a calculation on a set of values and return a single value. Some common aggregate functions include `COUNT`, `SUM`, `AVG`, `MAX`, and `MIN`.

- **COUNT()**: Returns the number of rows that matches a specified criterion.
  ```sql
  SELECT COUNT(*) FROM Students;
  ```

- **SUM()**: Returns the total sum of a numeric column.
  ```sql
  SELECT SUM(Age) FROM Students;
  ```

- **AVG()**: Returns the average value of a numeric column.
  ```sql
  SELECT AVG(Age) FROM Students;
  ```

- **MAX()**: Returns the maximum value in a set.
  ```sql
  SELECT MAX(Age) FROM Students;
  ```

- **MIN()**: Returns the minimum value in a set.
  ```sql
  SELECT MIN(Age) FROM Students;
  ```

### 3. Explain in detail about 1NF, 2NF and 3NF with suitable examples.

**First Normal Form (1NF):**
A table is in 1NF if:
- It only contains atomic (indivisible) values.
- Each column contains values of a single type.
- Each column must have a unique name.
- The order in which data is stored does not matter.

*Example:*
Consider a table with the following structure:

| StudentID | Name     | Subjects      |
|-----------|----------|---------------|
| 1         | John Doe | Math, Physics |
| 2         | Jane Doe | Chemistry     |

This table is not in 1NF because the `Subjects` column contains multiple values. To convert it to 1NF, each subject should be in a separate row.

| StudentID | Name     | Subject  |
|-----------|----------|----------|
| 1         | John Doe | Math     |
| 1         | John Doe | Physics  |
| 2         | Jane Doe | Chemistry|

**Second Normal Form (2NF):**
A table is in 2NF if:
- It is in 1NF.
- It has no partial dependencies; i.e., non-key attributes are fully dependent on the primary key.

*Example:*
Consider the 1NF table:

| StudentID | Name     | Subject  | Teacher      |
|-----------|----------|----------|--------------|
| 1         | John Doe | Math     | Mr. Smith    |
| 1         | John Doe | Physics  | Mrs. Johnson |
| 2         | Jane Doe | Chemistry| Dr. Brown    |

Here, `Name` depends only on `StudentID` but not on `Subject`. To bring this table to 2NF, separate `Student` and `Subject` details.

| StudentID | Name     |
|-----------|----------|
| 1         | John Doe |
| 2         | Jane Doe |

| StudentID | Subject  | Teacher      |
|-----------|----------|--------------|
| 1         | Math     | Mr. Smith    |
| 1         | Physics  | Mrs. Johnson |
| 2         | Chemistry| Dr. Brown    |

**Third Normal Form (3NF):**
A table is in 3NF if:
- It is in 2NF.
- It has no transitive dependencies; i.e., non-key attributes are not dependent on other non-key attributes.

*Example:*
Consider the 2NF tables:

| StudentID | Name     |
|-----------|----------|
| 1         | John Doe |
| 2         | Jane Doe |

| StudentID | Subject  | TeacherID |
|-----------|----------|-----------|
| 1         | Math     | 101       |
| 1         | Physics  | 102       |
| 2         | Chemistry| 103       |

| TeacherID | Teacher      |
|-----------|--------------|
| 101       | Mr. Smith    |
| 102       | Mrs. Johnson |
| 103       | Dr. Brown    |

Here, `Teacher` is dependent on `TeacherID`, not directly on `StudentID` or `Subject`. By creating a separate `Teacher` table, we eliminate the transitive dependency, thus achieving 3NF.
### 4. Explain 4NF, 5NF normal forms with examples.

**Fourth Normal Form (4NF):**
A table is in 4NF if:
- It is in Boyce-Codd Normal Form (BCNF).
- It has no multi-valued dependencies other than a candidate key.

*Example:*
Consider a table representing students' enrolled courses and their hobbies:

| StudentID | Course    | Hobby    |
| --------- | --------- | -------- |
| 1         | Math      | Reading  |
| 1         | Math      | Swimming |
| 1         | Physics   | Reading  |
| 1         | Physics   | Swimming |
| 2         | Chemistry | Dancing  |
| 2         | Chemistry | Painting |

Here, `Course` and `Hobby` are independent multi-valued attributes of `StudentID`. To achieve 4NF, we split the table into two:

Courses table:

| StudentID | Course    |
| --------- | --------- |
| 1         | Math      |
| 1         | Physics   |
| 2         | Chemistry |

Hobbies table:

| StudentID | Hobby       |
|-----------|-------------|
| 1         | Reading     |
| 1         | Swimming    |
| 2         | Dancing     |
| 2         | Painting    |

**Fifth Normal Form (5NF):**
A table is in 5NF if:
- It is in 4NF.
- It has no join dependencies; i.e., the table cannot be decomposed into smaller tables without loss of data.

*Example:*
Consider a table representing student project groups and the subjects they are working on:

| StudentID | ProjectGroup | Subject   |
| --------- | ------------ | --------- |
| 1         | A            | Math      |
| 1         | A            | Physics   |
| 2         | B            | Chemistry |
| 2         | B            | Biology   |

To achieve 5NF, decompose into smaller tables ensuring that no information is lost:

Student-Project table:

| StudentID | ProjectGroup |
|-----------|--------------|
| 1         | A            |
| 2         | B            |

Project-Subject table:

| ProjectGroup | Subject    |
|--------------|------------|
| A            | Math       |
| A            | Physics    |
| B            | Chemistry  |
| B            | Biology    |

### 5. Explain the following Operators in SQL with examples: i) SOME ii) IN iii) EXCEPT iv) UNION v) ANY vi) ALL

**i) SOME:**
The `SOME` operator is used to compare a value to each value in a list or result from a subquery. It returns true if at least one comparison is true.

*Example:*
```sql
SELECT StudentID, Age 
FROM Students 
WHERE Age > SOME (SELECT Age FROM Students WHERE Grade = 'B');
```
This query retrieves students whose age is greater than at least one student with grade 'B'.

**ii) IN:**
The `IN` operator is used to specify multiple values in a WHERE clause.

*Example:*
```sql
SELECT * 
FROM Students 
WHERE Name IN ('John Doe', 'Jane Doe');
```
This query retrieves students named 'John Doe' or 'Jane Doe'.

**iii) EXCEPT:**
The `EXCEPT` operator returns all distinct rows from the first query that are not in the result set of the second query.

*Example:*
```sql
SELECT StudentID 
FROM Students 
EXCEPT 
SELECT StudentID 
FROM Graduates;
```
This query retrieves student IDs that are in the Students table but not in the Graduates table.

**iv) UNION:**
The `UNION` operator is used to combine the result sets of two or more SELECT statements. It removes duplicate records.

*Example:*
```sql
SELECT StudentID 
FROM Students 
UNION 
SELECT StudentID 
FROM Alumni;
```
This query retrieves a combined list of student IDs from both the Students and Alumni tables, with duplicates removed.

**v) ANY:**
The `ANY` operator is used to compare a value to any value in a list or result from a subquery. It returns true if any one of the comparisons is true.

*Example:*
```sql
SELECT StudentID, Age 
FROM Students 
WHERE Age > ANY (SELECT Age FROM Students WHERE Grade = 'A');
```
This query retrieves students whose age is greater than any student with grade 'A'.

**vi) ALL:**
The `ALL` operator is used to compare a value to all values in another value set. It returns true if the comparison is true for all values in the list.

*Example:*
```sql
SELECT StudentID, Age 
FROM Students 
WHERE Age > ALL (SELECT Age FROM Students WHERE Grade = 'C');
```
This query retrieves students whose age is greater than all students with grade 'C'.

### 6. Explain in detail about Triggers and Active databases.

**Triggers:**
A trigger is a stored procedure in a database that automatically invokes or executes in response to certain events on a particular table or view. Common events include `INSERT`, `UPDATE`, and `DELETE`.

*Example:*
Creating a trigger to log changes in the `Students` table:
```sql
CREATE TABLE StudentLog (
    LogID INT PRIMARY KEY,
    StudentID INT,
    Action VARCHAR(50),
    ActionTime DATETIME
);

CREATE TRIGGER LogStudentChanges
AFTER INSERT ON Students
FOR EACH ROW
BEGIN
    INSERT INTO StudentLog (StudentID, Action, ActionTime)
    VALUES (NEW.StudentID, 'INSERT', NOW());
END;
```
This trigger logs every insertion into the `Students` table into the `StudentLog` table.

**Active Databases:**
Active databases are databases that include triggers, constraints, and other mechanisms to enforce business rules and data integrity automatically. They react to changes in the database without explicit request from the user.

*Features of Active Databases:*
- **Triggers**: Automatically execute specified actions in response to certain events.
- **Constraints**: Enforce rules at the database level (e.g., primary keys, foreign keys, checks).
- **Stored Procedures**: Precompiled collections of SQL statements that can be executed as a program.

**Advantages:**
- Enforce data integrity and business rules consistently.
- Reduce application code complexity by moving logic to the database.
- Improve performance by reducing round-trips between application and database.

# Unit 4
### 1. What is transaction? Explain the ACID properties of the transaction.

**What is a Transaction?**

A transaction in a database context is a sequence of one or more SQL operations (such as reads, writes, updates, etc.) executed as a single unit of work. A transaction ensures that either all operations within the sequence are completed successfully, or none of them are. Transactions are essential for maintaining data integrity and consistency in databases.

**ACID Properties:**

ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties ensure reliable transaction processing.

- **Atomicity:** This property ensures that a transaction is treated as a single unit, which either completes entirely or does not happen at all. If any part of the transaction fails, the entire transaction is rolled back.
  *Example:*
  ```sql
  START TRANSACTION;
  UPDATE Accounts SET balance = balance - 100 WHERE AccountID = 1;
  UPDATE Accounts SET balance = balance + 100 WHERE AccountID = 2;
  COMMIT;
  ```
  If the second update fails, the first update is rolled back.

- **Consistency:** This property ensures that a transaction takes the database from one consistent state to another. It ensures that the database remains consistent before and after the transaction.
  *Example:*
  A bank transfer ensures that the total amount of money in both accounts remains the same before and after the transaction.

- **Isolation:** This property ensures that transactions are executed in isolation from each other. Intermediate results within a transaction are invisible to other transactions.
  *Example:*
  If two transactions are updating the same account balance, isolation ensures that one transaction does not see the partial updates of the other.

- **Durability:** This property ensures that once a transaction has been committed, it remains so, even in the event of a system failure. The changes made by the transaction are permanently recorded.
  *Example:*
  Once a bank transfer transaction is committed, the changes to account balances are permanent, even if the system crashes immediately after.

###  2. Explain multiple granularity of locking protocol with example. 

Multiple granularity locking allows transactions to lock objects at different levels of granularity, such as the entire database, a table, a page, or a row. This protocol helps in improving the performance by allowing different transactions to operate on different levels of data.

**Types of Locks:**
- **Intention Locks:** Used to indicate the intention to acquire more granular locks.
  - `IS (Intention Shared)`: Intention to acquire shared locks on finer granularity.
  - `IX (Intention Exclusive)`: Intention to acquire exclusive locks on finer granularity.
  - `SIX (Shared and Intention Exclusive)`: Acquires a shared lock and intention exclusive locks on finer granularity.
- **Shared Lock (S):** Allows the transaction to read but not modify the locked item.
- **Exclusive Lock (X):** Allows the transaction to read and modify the locked item.

**Example:**
Consider a database with a hierarchy of a database (DB), tables (T1, T2), and rows (R1, R2).

1. **Transaction T1 wants to read Table T1:**
   - Acquires `IS` lock on DB.
   - Acquires `S` lock on T1.

2. **Transaction T2 wants to update Row R1 in Table T1:**
   - Acquires `IX` lock on DB.
   - Acquires `IX` lock on T1.
   - Acquires `X` lock on R1.

This protocol ensures that if a transaction has a lock on a higher-level object, it has the appropriate intention locks on the lower-level objects to prevent conflicting access by other transactions.

### 3. What is serializability? Explain Conflict serializability with an example.

**Serializability:**

Serializability is a concept in database concurrency control that ensures that a schedule (sequence of operations from multiple transactions) results in a consistent database state. A schedule is serializable if it produces the same result as some serial execution of the transactions.

**Conflict Serializability:**

Conflict serializability is a type of serializability that ensures a schedule can be transformed into a serial schedule by swapping non-conflicting operations.

**Conflict:**
Two operations conflict if they:
1. Belong to different transactions.
2. Access the same data item.
3. At least one of the operations is a write.

**Example:**

Consider two transactions T1 and T2:
- T1: Read(A), Write(A)
- T2: Read(A), Write(A)

**Non-Serializable Schedule:**
```
T1: Read(A)
T2: Read(A)
T2: Write(A)
T1: Write(A)
```

**Conflict Pairs:**
- `T1 Read(A)` and `T2 Write(A)`
- `T2 Read(A)` and `T1 Write(A)`

This schedule is not serializable because there is no way to swap the operations to achieve a serial order without changing the final outcome.

**Serializable Schedule:**
```
T1: Read(A)
T1: Write(A)
T2: Read(A)
T2: Write(A)
```
or
```
T2: Read(A)
T2: Write(A)
T1: Read(A)
T1: Write(A)
```

In both cases, the operations are in a serial order, and the final result will be consistent with a serial execution of T1 and T2.
### 4. What is Transaction? Explain the life cycle of the transaction with a neat diagram.

**What is a Transaction?**

A transaction is a unit of work that consists of a sequence of one or more operations performed on a database. Transactions ensure data integrity and consistency by adhering to the ACID properties: Atomicity, Consistency, Isolation, and Durability.

**Life Cycle of a Transaction:**

1. **Active:** The transaction is being executed.
2. **Partially Committed:** All operations have been executed, and the transaction is waiting for a commit.
3. **Committed:** The transaction has been successfully completed, and changes are made permanent.
4. **Failed:** The transaction cannot proceed due to an error.
5. **Aborted:** The transaction has been rolled back, and changes are undone.
6. **Terminated:** The transaction has ended (either committed or aborted).

**Diagram:**
![800](https://media.geeksforgeeks.org/wp-content/uploads/20230915172115/Transaction-in-dbms.png)

![[Pasted image 20240718200318.png]]
### 5. Discuss about transaction recovery techniques.

Transaction recovery techniques are essential for maintaining the integrity and consistency of a database in the event of a failure. They ensure that the database can recover to a consistent state.

**Types of Failures:**

1. **Transaction Failures:** Logical errors or system crashes.
2. **System Failures:** Hardware or software failures.
3. **Media Failures:** Disk crashes or data corruption.

**Recovery Techniques:**

1. **Log-Based Recovery:** 
   - **Write-Ahead Logging (WAL):** Before any changes are made to the database, the changes are first recorded in a log.
   - **Undo Logging:** Logs before values (old values) to undo changes if a transaction fails.
   - **Redo Logging:** Logs after values (new values) to redo changes if a transaction commits.

   *Example:*
   ```plaintext
   T1: Start
   T1: Write X (X=100 -> X=150)
   Log: <T1, X, 100>
   T1: Commit
   ```

2. **Checkpointing:**
   - Periodically save the current state of the database and the transaction log to disk.
   - During recovery, the system can start from the last checkpoint, reducing the amount of log data to process.

   *Example:*
   ```plaintext
   [Checkpoint] T1, T2 active
   ```

3. **Shadow Paging:**
   - Maintain two versions of the database: the current page table and the shadow page table.
   - Changes are made to the current page table. If the transaction commits, the shadow page table is updated.

   *Example:*
   ```plaintext
   Current Page Table: P1, P2, P3
   Shadow Page Table:  S1, S2, S3
   ```

4. **Deferred Update:**
   - All changes are kept in a buffer until the transaction reaches the commit point.
   - Once committed, the changes are written to the database.

   *Example:*
   ```plaintext
   Buffer: Write X=150
   Commit: Apply changes to database
   ```

5. **Immediate Update:**
   - Changes are applied immediately to the database but are logged so they can be undone if necessary.

   *Example:*
   ```plaintext
   Write X=150 (log the old value X=100)
   ```

### 6. What is a lock in DBMS? Discuss different types of locks in DBMS.

**What is a Lock in DBMS?**

A lock is a mechanism used to control concurrent access to data in a database. Locks prevent conflicts when multiple transactions try to access the same data simultaneously, ensuring data integrity and consistency.

**Types of Locks:**

1. **Binary Locks:**
   - **Lock:** The data item is locked.
   - **Unlock:** The data item is unlocked.
   
   *Example:*
   ```plaintext
   Lock(X)
   Unlock(X)
   ```

2. **Shared and Exclusive Locks:**
   - **Shared Lock (S):** Multiple transactions can read the data item.
   - **Exclusive Lock (X):** Only one transaction can write to the data item.

   *Example:*
   ```plaintext
   S(X)  // Shared lock on X
   X(X)  // Exclusive lock on X
   ```

3. **Intention Locks:**
   - **Intention Shared (IS):** Intent to acquire a shared lock on a lower-level node.
   - **Intention Exclusive (IX):** Intent to acquire an exclusive lock on a lower-level node.
   - **Shared Intention Exclusive (SIX):** Shared lock on the node with intention exclusive locks on lower-level nodes.
   
   *Example:*
   ```plaintext
   IS(DB)  // Intent to acquire shared lock on a table within DB
   IX(DB)  // Intent to acquire exclusive lock on a table within DB
   ```

4. **Degree of Locking (Granularity):**
   - Locks can be applied at various levels of granularity: Database, Table, Page, Row, etc.
   
   *Example:*
   ```plaintext
   Database Lock (DB)
   Table Lock (T)
   Page Lock (P)
   Row Lock (R)
   ```

5. **Two-Phase Locking Protocol (2PL):**
   - **Growing Phase:** Transaction acquires all necessary locks.
   - **Shrinking Phase:** Transaction releases locks and cannot acquire new ones.

   *Example:*
   ```plaintext
   Growing Phase: Lock(X), Lock(Y)
   Shrinking Phase: Unlock(X), Unlock(Y)
   ```

6. **Deadlock and Deadlock Resolution:**
   - **Deadlock:** Occurs when two or more transactions wait for each other to release locks.
   - **Resolution Techniques:**
     - **Timeouts:** Abort transactions that have been waiting for too long.
     - **Deadlock Detection and Recovery:** Periodically check for deadlocks and abort one or more transactions to resolve them.
   
   *Example:*
   ```plaintext
   Transaction T1 locks X, waits for Y.
   Transaction T2 locks Y, waits for X.
   ```

# Unit 5
### 1. Define File Organization. Explain about types of file organization.

**Definition:**
File organization refers to the way data is stored in a file so that it can be efficiently accessed and managed. Different file organization techniques are used to optimize the performance of data retrieval, insertion, deletion, and updating.

**Types of File Organization:**

1. **Heap (Unordered) File Organization:**
   - Records are placed in the file in the order they are inserted.
   - No particular ordering of records.
   - Suitable for small tables or when the entire table is frequently scanned.
   - Pros: Simple to implement, efficient for bulk loading.
   - Cons: Inefficient for search and update operations.

   *Example:* An employee table where records are added as they come.

2. **Sequential (Ordered) File Organization:**
   - Records are stored in a sequential order based on the value of a sorting key.
   - Efficient for range queries and ordered access.
   - Pros: Good for search operations using the sorting key.
   - Cons: Insertions and deletions can be slow due to the need to maintain order.

   *Example:* A student table sorted by student ID.

3. **Indexed File Organization:**
   - Uses an index to locate records quickly.
   - Index is a separate file that contains references (pointers) to the records.
   - Pros: Fast access to records using the index.
   - Cons: Extra storage required for the index.

   *Example:* An index on a customer table based on customer ID.

4. **Clustered File Organization:**
   - Records that are related are stored together.
   - Can be implemented using primary or secondary indices.
   - Pros: Efficient for queries that involve related records.
   - Cons: Complexity in maintaining clusters.

   *Example:* An orders table where orders from the same customer are stored together.

5. **Hashed File Organization:**
   - Records are placed based on a hash function applied to a key field.
   - Provides direct access to records.
   - Pros: Very efficient for equality searches.
   - Cons: Less efficient for range queries.

   *Example:* A product table where records are placed based on a hash of the product ID.

### 2. Define Indexing and explain about types of indexing.

**Definition:**
Indexing is a data structure technique that improves the speed of data retrieval operations on a database table. An index is a copy of selected columns of data from a table that is designed to speed up retrieval.
![800](https://cdn1.byjus.com/wp-content/uploads/2022/05/word-image195.png)
**Types of Indexing:**

1. **Primary Index:**
   - Built on the primary key of the table.
   - Each index entry points to the data block containing the actual record.
   - One-to-one mapping between index entries and data records.

   *Example:* Index on the `EmployeeID` column in an employee table.

2. **Secondary Index:**
   - Built on non-primary key columns.
   - There can be multiple secondary indices on a table.
   - One-to-many mapping between index entries and data records.

   *Example:* Index on the `LastName` column in an employee table.

3. **Clustered Index:**
   - The order of the rows in the table corresponds to the order of the rows in the index.
   - Only one clustered index per table since it defines the physical storage order.

   *Example:* Index on the `OrderDate` column in an orders table.

4. **Non-clustered Index:**
   - Separate from the actual data rows.
   - Can have multiple non-clustered indices on a table.
   - Index entries contain pointers to the data rows.

   *Example:* Index on the `Email` column in a user table.

5. **Composite Index:**
   - Built on multiple columns of a table.
   - Useful for queries that filter on more than one column.

   *Example:* Index on the `FirstName` and `LastName` columns in a contacts table.

### 3. What is Hashing? Explain in detail about hashing techniques.

**Definition:**
Hashing is a technique used to map data of arbitrary size to fixed-size values (hash values or hash codes). In databases, hashing is used to quickly locate a data record given its search key.
![800](https://media.geeksforgeeks.org/wp-content/uploads/20231026004607/directories.png)
**Hashing Techniques:**

1. **Static Hashing:**
   - The number of primary pages (buckets) is fixed.
   - A hash function maps keys to a fixed number of buckets.
   - Can lead to overflow pages when a bucket gets full (handled by overflow chaining).

   *Example:* A hash table with 10 buckets using a hash function `h(key) = key % 10`.

2. **Dynamic Hashing:**
   - The number of buckets can grow or shrink dynamically.
   - Common techniques include Extendible Hashing and Linear Hashing.

   **Extendible Hashing:**
   - Uses a directory to map hash values to buckets.
   - The directory can grow in size, and buckets can be split as needed.
   - Example: Initially, two buckets with a hash function based on the first bit of the key. As buckets fill up, more bits are used.

   **Linear Hashing:**
   - Buckets are split in a linear order.
   - Uses a level indicator to decide when to split buckets.
   - Example: Initially, one bucket with a hash function `h0(key) = key % 1`. As records increase, split the bucket and use `h1(key) = key % 2`.

3. **Open Addressing:**
   - All elements are stored in the hash table itself.
   - When a collision occurs, it probes for the next empty slot.
   - Techniques include Linear Probing, Quadratic Probing, and Double Hashing.

   **Linear Probing:**
   - If a collision occurs at `h(key)`, check the next slot `h(key) + 1`, `h(key) + 2`, etc.
   - Example: For a key that hashes to position 3, if position 3 is occupied, check positions 4, 5, etc.

   **Quadratic Probing:**
   - Probes at intervals of `1^2, 2^2, 3^2, ...` slots.
   - Example: For a key that hashes to position 3, if position 3 is occupied, check positions `3 + 1^2`, `3 + 2^2`, `3 + 3^2`, etc.

   **Double Hashing:**
   - Uses two hash functions.
   - If a collision occurs at `h1(key)`, the next position is determined by `h2(key)`.
   - Example: First hash `h1(key) = key % 10`, second hash `h2(key) = 1 + (key % 9)`.

### 4. What is a B+ tree? Explain in detail the operations of B+ trees. 

**What is a B+ Tree?**

A B+ Tree is a type of self-balancing tree data structure that maintains sorted data and allows for efficient insertion, deletion, and search operations. It is an extension of the B-Tree and is commonly used in databases and file systems. Unlike B-Trees, all values in a B+ Tree are stored at the leaf level, and internal nodes only store keys to guide the search.
![800](https://www.tutorialspoint.com/data_structures_algorithms/images/bplus_trees.jpg)
**Characteristics of B+ Trees:**

1. **Balanced Tree Structure:** All leaf nodes are at the same level.
2. **Ordered:** Keys are maintained in a sorted order.
3. **Nodes:** Internal nodes store keys and pointers, while leaf nodes store keys and values.
4. **Linked Leaves:** Leaf nodes are linked together, facilitating range queries.
5. **Degree:** Each node can have a minimum and maximum number of children, defined by the tree's degree \( m \).

**Operations on B+ Trees:**

1. **Search Operation:**
   - Begin at the root node and compare the search key with the keys in the node.
   - Follow the appropriate pointer (child) based on the comparison.
   - Repeat the process until a leaf node is reached.
   - Search the leaf node for the key.

   **Example:**
   ```plaintext
   Search for key 45:
   - Start at root: Compare 45 with keys.
   - Move to appropriate child node.
   - Continue until reaching the leaf.
   - Locate key 45 in the leaf node.
   ```

2. **Insertion Operation:**
   - Start at the root and find the appropriate leaf node where the key should be inserted.
   - Insert the key in the leaf node in the correct sorted order.
   - If the leaf node overflows (exceeds the maximum allowed keys), split the leaf node.
     - Insert the middle key into the parent node.
     - If the parent node overflows, repeat the splitting process up the tree.
   - Adjust pointers to maintain the structure.

   **Example:**
   ```plaintext
   Insert key 25:
   - Locate the leaf node for insertion.
   - Insert 25 in the correct order.
   - If the leaf node overflows, split and promote the middle key to the parent.
   - Repeat if necessary up to the root.
   ```

3. **Deletion Operation:**
   - Locate the key to be deleted in the leaf node.
   - Remove the key from the leaf node.
   - If the leaf node underflows (has fewer than the minimum allowed keys), rebalance by:
     - Redistributing keys from adjacent siblings.
     - Merging with a sibling if redistribution is not possible.
   - Adjust pointers and keys in parent nodes as necessary.

   **Example:**
   ```plaintext
   Delete key 30:
   - Locate key 30 in the leaf node.
   - Remove key 30.
   - If the leaf node underflows, redistribute keys with siblings or merge nodes.
   - Update parent nodes as needed.
   ```

### 5. Explain about Indexed sequential access method (ISAM).

**What is ISAM?**

Indexed Sequential Access Method (ISAM) is a file organization method that combines the benefits of both sequential and direct access. It allows for efficient searching, insertion, deletion, and updates of records in a file by using an index to quickly locate data.

![800](https://static.javatpoint.com/dbms/images/dbms-indexed-sequential-access-method.png)
**Characteristics of ISAM:**

1. **Primary Index:** A primary index is built on the primary key of the file.
2. **Overflow Areas:** When a data block (bucket) is full, additional records are stored in an overflow area.
3. **Sequential Access:** Records can be accessed sequentially using pointers.
4. **Static Structure:** The structure of ISAM is relatively static, making it suitable for files with infrequent updates.

**Structure of ISAM:**

1. **Index Levels:**
   - **Primary Index:** Points to data blocks (buckets).
   - **Secondary Index (optional):** May be used for faster access.

2. **Data Blocks (Buckets):** Store the actual records.
3. **Overflow Blocks:** Store records that cannot fit into their designated data blocks.

**Operations in ISAM:**

1. **Search Operation:**
   - Use the primary index to find the appropriate data block.
   - Search within the data block for the desired record.
   - If the record is not found, follow pointers to overflow blocks if they exist.

   **Example:**
   ```plaintext
   Search for key 75:
   - Use the primary index to locate the data block.
   - Search the data block for key 75.
   - If not found, check overflow blocks.
   ```

2. **Insertion Operation:**
   - Locate the appropriate data block using the primary index.
   - Insert the record into the data block if space is available.
   - If the data block is full, add the record to the overflow block.
   - Update pointers as necessary.

   **Example:**
   ```plaintext
   Insert key 60:
   - Locate the data block using the primary index.
   - Insert 60 into the data block.
   - If the data block is full, insert 60 into an overflow block.
   - Update pointers.
   ```

3. **Deletion Operation:**
   - Locate the record using the primary index and data block.
   - Remove the record from the data block or overflow block.
   - If necessary, reorganize the data block or overflow block to maintain efficiency.

   **Example:**
   ```plaintext
   Delete key 45:
   - Locate key 45 using the primary index.
   - Remove key 45 from the data block or overflow block.
   - Reorganize blocks if needed.
   ```

4. **Update Operation:**
   - Locate the record using the primary index and data block.
   - Update the record in the data block or overflow block.
   - If the update causes the record to be moved, handle as an insertion and deletion.

   **Example:**
   ```plaintext
   Update key 80 to 85:
   - Locate key 80 using the primary index.
   - Update the record to 85.
   - If the data block changes, handle the update as an insertion and deletion.
   ```

**Advantages of ISAM:**

1. Efficient for both sequential and random access.
2. Suitable for read-mostly workloads with infrequent updates.
3. Simple and straightforward implementation.

**Disadvantages of ISAM:**

1. Static structure makes handling frequent updates challenging.
2. Overflow areas can become fragmented over time, reducing efficiency.
3. Requires periodic reorganization to maintain performance.

