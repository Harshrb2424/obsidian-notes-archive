#### Form of Basic SQL Query

A basic SQL query retrieves data from a database. It typically follows this structure:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

- **SELECT**: Specifies which columns to retrieve data from.
  - Example: `SELECT name, age FROM students;`

- **FROM**: Specifies the table(s) from which to retrieve data.
  - Example: `FROM employees;`

- **WHERE**: Optional clause to filter rows based on a condition.
  - Example: `WHERE age > 25;`

##### Examples:

1. Retrieve all columns from a table:
   ```sql
   SELECT * FROM employees;
   ```

2. Retrieve specific columns with conditions:
   ```sql
   SELECT name, salary
   FROM employees
   WHERE department = 'IT' AND salary > 50000;
   ```

#### UNION, INTERSECT, and EXCEPT

These operators are used to combine or compare the results of two or more SELECT queries.

- **UNION**: Combines the results of two or more SELECT statements into a single result set.
  
  ```sql
  SELECT column1 FROM table1
  UNION
  SELECT column1 FROM table2;
  ```
  - Removes duplicates by default.

- **INTERSECT**: Returns only rows that are present in both result sets of two SELECT statements.
  
  ```sql
  SELECT column1 FROM table1
  INTERSECT
  SELECT column1 FROM table2;
  ```

- **EXCEPT**: Returns only distinct rows from the left SELECT statement that are not in the right SELECT statement.
  
  ```sql
  SELECT column1 FROM table1
  EXCEPT
  SELECT column1 FROM table2;
  ```

##### Examples:

1. Using UNION to combine results:
   ```sql
   SELECT name FROM employees
   UNION
   SELECT name FROM contractors;
   ```

2. Using INTERSECT to find common records:
   ```sql
   SELECT name FROM employees
   INTERSECT
   SELECT name FROM contractors;
   ```

3. Using EXCEPT to find records in the first query but not in the second:
   ```sql
   SELECT name FROM employees
   EXCEPT
   SELECT name FROM contractors;
   ```

- **Syntax**: SQL syntax may vary slightly between database systems (e.g., MySQL, PostgreSQL, SQL Server).
- **Performance**: UNION, INTERSECT, and EXCEPT operations can impact query performance, especially with large datasets.
- **Set Operations**: These operators treat query results as sets, with UNION removing duplicates by default.
### Nested Queries

Nested queries (or subqueries) are SQL queries embedded within another query's WHERE clause or SELECT statement. They can be used to retrieve results based on conditions derived from another query.

#### Types of Nested Queries:

1. **Single-Row Subquery**: Returns zero or one row to the outer query.
   
   Example:
   ```sql
   SELECT name
   FROM employees
   WHERE department_id = (SELECT department_id FROM departments WHERE name = 'IT');
   ```

2. **Multiple-Row Subquery**: Returns multiple rows to the outer query.
   
   Example:
   ```sql
   SELECT name
   FROM employees
   WHERE department_id IN (SELECT department_id FROM departments WHERE location = 'New York');
   ```

3. **Correlated Subquery**: References columns from the outer query, executing once for each row processed by the outer query.
   
   Example:
   ```sql
   SELECT name
   FROM employees e
   WHERE salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);
   ```

#### Benefits of Nested Queries:

- **Modularity**: Breaks down complex tasks into simpler, manageable parts.
- **Flexibility**: Allows dynamic conditions based on results of other queries.
- **Optimization**: Can sometimes be optimized by the database engine for better performance.

### Aggregation Operators

Aggregation operators perform calculations on groups of rows to return a single value per group.

#### Common Aggregation Functions:

1. **COUNT()**: Returns the number of rows in a group.
   
   Example:
   ```sql
   SELECT COUNT(*) FROM employees;
   ```

2. **SUM()**: Returns the sum of values in a numeric column.
   
   Example:
   ```sql
   SELECT SUM(salary) FROM employees;
   ```

3. **AVG()**: Returns the average value of a numeric column.
   
   Example:
   ```sql
   SELECT AVG(salary) FROM employees;
   ```

4. **MIN()**: Returns the minimum value in a column.
   
   Example:
   ```sql
   SELECT MIN(salary) FROM employees;
   ```

5. **MAX()**: Returns the maximum value in a column.
   
   Example:
   ```sql
   SELECT MAX(salary) FROM employees;
   ```

#### Usage and Considerations:

- **GROUP BY Clause**: Used to group rows that have the same values into summary rows.
  
  Example:
  ```sql
  SELECT department_id, AVG(salary)
  FROM employees
  GROUP BY department_id;
  ```

- **HAVING Clause**: Used with GROUP BY to filter groups based on specified conditions.
  
  Example:
  ```sql
  SELECT department_id, AVG(salary)
  FROM employees
  GROUP BY department_id
  HAVING AVG(salary) > 50000;
  ```


- **Performance**: Aggregation operations can significantly impact performance, especially with large datasets. Indexes and query optimization are crucial.
- **Syntax Variations**: SQL syntax for nested queries and aggregation functions may vary slightly between database systems.
- **Data Integrity**: Ensure that nested queries and aggregation functions align with data integrity constraints to avoid unexpected results.

### NULL Values

In SQL, NULL represents a missing or unknown value. Understanding how NULL values behave and how to handle them is crucial for database management.

#### Characteristics of NULL:

- **Not a Value**: NULL is not equal to any value, including itself.
- **Handling NULL**:
  - Use `IS NULL` or `IS NOT NULL` to check for NULL values.
  - Handle NULLs appropriately in calculations and comparisons to avoid unexpected results.

#### Examples:

1. **Checking for NULL**:
   ```sql
   SELECT * FROM employees WHERE department_id IS NULL;
   ```

2. **Dealing with NULL in Calculations**:
   ```sql
   SELECT AVG(salary) FROM employees WHERE commission_pct IS NOT NULL;
   ```

### Complex Integrity Constraints in SQL

SQL supports various constraints to enforce data integrity rules, ensuring data accuracy and consistency across tables.

#### Types of Constraints:

1. **PRIMARY KEY**: Ensures each row in a table is uniquely identifiable.
   
   Example:
   ```sql
   CREATE TABLE employees (
       employee_id INT PRIMARY KEY,
       name VARCHAR(100),
       ...
   );
   ```

2. **FOREIGN KEY**: Establishes a link between tables, enforcing referential integrity.
   
   Example:
   ```sql
   CREATE TABLE orders (
       order_id INT PRIMARY KEY,
       customer_id INT,
       ...
       FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
   );
   ```

3. **CHECK Constraint**: Validates the values that can be inserted into a column.
   
   Example:
   ```sql
   CREATE TABLE employees (
       ...
       salary DECIMAL(10,2) CHECK (salary >= 0)
   );
   ```

4. **UNIQUE Constraint**: Ensures all values in a column or a set of columns are distinct.
   
   Example:
   ```sql
   CREATE TABLE departments (
       department_id INT PRIMARY KEY,
       department_name VARCHAR(100) UNIQUE
   );
   ```

### Triggers and Active Databases

Triggers are special types of stored procedures that automatically execute in response to specific events (e.g., INSERT, UPDATE, DELETE) on a particular table.

#### Components of Triggers:

- **Event**: Specifies when the trigger should execute (e.g., BEFORE INSERT, AFTER UPDATE).
- **Condition**: Specifies the condition that triggers the execution of the trigger.
- **Action**: Defines the task or operation the trigger performs when it fires.

#### Example:

```sql
CREATE TRIGGER audit_employee_changes
AFTER UPDATE ON employees
FOR EACH ROW
BEGIN
    INSERT INTO audit_log (employee_id, change_date, action)
    VALUES (OLD.employee_id, NOW(), 'Update');
END;
```

#### Benefits of Triggers:

- **Data Auditing**: Capture and log changes made to critical data.
- **Data Validation**: Enforce complex business rules and data integrity constraints.
- **Automation**: Automate routine tasks based on database events.

### Schema Refinement

Schema refinement in database design involves improving the design of database schemas to minimize redundancy, ensure data integrity, and optimize query performance.

#### Problems Caused by Redundancy

1. **Data Inconsistency**: Redundant data can lead to inconsistencies where updating one instance of data does not update all instances.
   
2. **Storage Overhead**: Redundant data requires more storage space, which can impact performance and increase storage costs.

3. **Update Anomalies**: Inefficient update operations where updates to data need to be applied to multiple places, increasing the risk of inconsistencies.

#### Decompositions

Decomposition involves breaking down a relation into smaller, more manageable relations to achieve a more refined database schema.

1. **Functional Dependencies**: Identify functional dependencies within the relation to guide decomposition decisions.

2. **Normalization**: Normalize relations to eliminate anomalies and redundancy, typically up to the Boyce-Codd Normal Form (BCNF) or Third Normal Form (3NF).

#### Problems Related to Decomposition

1. **Loss of Information**: Incorrect decomposition can lead to the loss of functional dependencies or information that was present in the original relation.

2. **Join Overhead**: Decomposed relations may require joins to reconstruct the original data, which can impact query performance.

3. **Dependency Preservation**: Ensuring that all functional dependencies from the original relation are preserved in the decomposed relations.

### Example Scenario:

Consider a database for a university where each student has a unique student ID, and courses are offered by multiple departments. A simplified example might look like this:

- **Students** (student_id, name, department_id)
- **Courses** (course_id, course_name, department_id)
- **Departments** (department_id, department_name)

#### Redundancy Example:

If `department_name` is stored in both `Students` and `Courses` tables, it introduces redundancy. Instead, `department_id` can be used as a foreign key to reference the `Departments` table, reducing redundancy.

#### Decomposition Example:

If a relation has functional dependencies like `student_id -> name` and `department_id -> department_name`, it might be decomposed into:
- **Students** (student_id, name, department_id)
- **Departments** (department_id, department_name)


### Reasoning About Functional Dependencies

Functional dependencies (FDs) describe relationships between attributes in a relation. A functional dependency \( X \rightarrow Y \) means that for every unique value of \( X \), there is a unique corresponding value of \( Y \). Understanding and reasoning about functional dependencies helps in designing normalized database schemas to ensure data integrity and reduce redundancy.

#### Example of Functional Dependency:

In a relation \( R(A, B, C) \):
- \( A \rightarrow B \) means every unique value of \( A \) determines a unique value of \( B \).

#### Reasoning:

1. **Identifying Dependencies**: Analyze how attributes depend on each other based on business rules and data semantics.
   
2. **Normalization**: Use functional dependencies to decompose relations into smaller, well-structured relations to minimize redundancy and anomalies.

### Normal Forms

#### First Normal Form (1NF)

1NF ensures that each column in a table contains atomic (indivisible) values and that there are no repeating groups or arrays of data.

- **Example Violation**: Storing multiple values in a single column, such as storing comma-separated values.

#### Second Normal Form (2NF)

2NF builds on 1NF and eliminates partial dependencies. It requires that every non-key attribute is fully functionally dependent on the entire primary key.

- **Example**: A composite primary key where each attribute contributes to identifying a row uniquely.

#### Third Normal Form (3NF)

3NF further refines the normalization process by eliminating transitive dependencies. It requires that every non-key attribute is non-transitively dependent on the primary key.

- **Example**: Ensuring that non-key attributes depend only on the primary key, not on other non-key attributes.

### Boyce-Codd Normal Form (BCNF)

BCNF is a stricter form of 3NF, where every determinant (attribute determining another attribute) is a candidate key. It addresses certain cases that 3NF does not cover comprehensively.

- **Example**: Ensuring that every functional dependency is a candidate key, thereby avoiding redundancy and ensuring data integrity.

### Example Scenario:

Consider a simplified database schema for a company's employees and departments:

- **Employees** (employee_id, employee_name, department_id, salary)
- **Departments** (department_id, department_name)

#### Example Functional Dependencies:

- \( employee_id \rightarrow employee_name \): Each employee ID uniquely determines the employee's name.
- \( department_id \rightarrow department_name \): Each department ID uniquely determines the department's name.

#### Normalization Steps:

1. **1NF**: Ensure each attribute contains atomic values.
2. **2NF**: Remove partial dependencies by ensuring non-key attributes depend on the entire primary key.
3. **3NF**: Eliminate transitive dependencies by ensuring non-key attributes depend only on the primary key.

#### BCNF Consideration:

If a relation satisfies 3NF but still has multiple candidate keys where not all determinants are candidate keys, BCNF ensures that all functional dependencies are based on candidate keys only.

### Lossless Join Decomposition

Lossless Join Decomposition is a property in database normalization where decomposing a relation into smaller relations (tables) ensures that the original relation can be reconstructed (joined) without losing any information. This property is crucial for maintaining data integrity and ensuring that the decomposition process does not introduce anomalies or data loss.

#### Key Points:

1. **Definition**: A decomposition of a relation \( R \) into relations \( R1 \) and \( R2 \) is lossless join if every instance \( r \) of \( R \) can be reconstructed by joining \( R1 \) and \( R2 \) using a common attribute.

2. **Algorithms**: Algorithms such as the Chase test or dependency-preserving decomposition techniques are used to verify and achieve lossless join decomposition.

3. **Normalization Context**: Lossless join decomposition is typically considered alongside functional dependencies and normal forms to ensure database schemas are well-structured and free from redundancy and anomalies.

### Multivalued Dependencies (MVDs)

Multivalued Dependencies are constraints that apply to a set of attributes in a relation, specifying that certain attributes can have multiple values independent of each other. Understanding and managing MVDs is important for database designers to ensure data integrity and proper normalization.

#### Key Points:

1. **Definition**: An MVD \( X \rightarrow\!\!\!\!\!\!\rightarrow Y \) states that for every unique value of \( X \), there is a set of corresponding values of \( Y \) that are independent of each other.

2. **Example**: In a relation \( R(A, B, C) \), if \( A \rightarrow\!\!\!\!\!\!\rightarrow B \), then for each unique \( A \) value, there can be multiple independent values of \( B \).

3. **Normalization**: MVDs are typically addressed during the process of database normalization, often leading to the creation of additional relations to handle the dependencies properly.

### Example Scenario:

Consider a database schema for managing sales orders:

- **Orders** (order_id, customer_id, product_id, order_date, ship_date, quantity)

#### Lossless Join Decomposition Example:

If we decompose the relation \( Orders \) into \( Orders1(order_id, customer_id, product_id) \) and \( Orders2(order_id, order_date, ship_date, quantity) \), we can join \( Orders1 \) and \( Orders2 \) using \( order_id \) to reconstruct the original \( Orders \) relation without losing any information.

#### Multivalued Dependency Example:

If \( customer_id \rightarrow\!\!\!\!\!\!\rightarrow product_id \) exists in \( Orders \), it means that for each customer, there can be multiple products they are interested in ordering, independent of each other.

### Fourth Normal Form (4NF)

Fourth Normal Form (4NF) is an extension of the Third Normal Form (3NF) and addresses certain types of complex relationships and multivalued dependencies that are not handled by 3NF.

#### Key Points:

1. **Definition**: A relation is in 4NF if it is in 3NF and has no non-trivial multivalued dependencies (MVDs).

2. **Multivalued Dependencies**: In 4NF, every non-trivial MVD must be a dependency of the candidate key.

3. **Reduction of Redundancy**: 4NF helps in further reducing redundancy and anomalies by ensuring that all dependencies are properly managed.

#### Example Scenario:

Consider a relation \( R(A, B, C) \):
- If \( A \rightarrow B \) and \( A \rightarrow\!\!\!\!\!\!\rightarrow C \), then \( R \) is in 3NF but not in 4NF because \( C \) is not functionally dependent on \( A \).

### Fifth Normal Form (5NF)

Fifth Normal Form (5NF), also known as Project-Join Normal Form (PJNF), deals with cases where certain join dependencies exist in a relation, particularly where the relation cannot be further decomposed without losing information.

#### Key Points:

1. **Definition**: A relation is in 5NF if it is in 4NF and every join dependency in the relation is a consequence of the candidate keys.

2. **Join Dependencies**: 5NF ensures that all join dependencies are explicitly stated and cannot be decomposed further without losing information.

3. **Complex Relationships**: 5NF handles complex relationships and dependencies that may arise in real-world database scenarios.

#### Example Scenario:

Consider a relation \( R(A, B, C) \):
- If \( A \rightarrow\!\!\!\!\!\!\rightarrow B \) and \( B \rightarrow\!\!\!\!\!\!\rightarrow C \), then \( R \) is in 5NF because all join dependencies are consequences of the candidate keys.

