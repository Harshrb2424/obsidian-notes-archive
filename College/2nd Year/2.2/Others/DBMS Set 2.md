**a) In the process of computerization in colleges , draw an ER diagram to design a database which consists database for student, staff, departments, and administration details.**
**b) create table emp_salary with the following attributes (empcode, dob,dept, salary)**
**c) insert 5 rows and rename empsalary to emp_info;**
**d) find the  sum of salaries, least and highest salaries that an employee draws.**
**e) List all the salaries in ascending order.**
**f)create view and write the syntax of view**

### a) ER Diagram for College Database

The ER diagram for a college database would include entities such as Student, Staff, Department, and Administration, along with their relationships.

**Entities and Attributes:**
- **Student**: `Student_ID`, `Name`, `DOB`, `Dept_ID`
- **Staff**: `Staff_ID`, `Name`, `DOB`, `Dept_ID`
- **Department**: `Dept_ID`, `Dept_Name`, `Head_ID` (Staff_ID as foreign key)
- **Administration**: `Admin_ID`, `Name`, `Role`

**Relationships:**
- A **Student** belongs to a **Department**.
- A **Staff** works in a **Department**.
- **Administration** manages **Departments** and other entities.

**ER Diagram:**

![[Pasted image 20240722220853.png]]
### b) Create Table `emp_salary`

```sql
CREATE TABLE emp_salary (
    empcode INT PRIMARY KEY,
    dob DATE,
    dept VARCHAR(50),
    salary DECIMAL(10, 2)
);
```

### c) Insert Rows and Rename Table to `emp_info`

**Insert 5 Rows:**
```sql
INSERT INTO emp_salary (empcode, dob, dept, salary) VALUES 
(1, '1985-01-23', 'HR', 50000),
(2, '1990-07-15', 'Finance', 60000),
(3, '1988-03-10', 'IT', 55000),
(4, '1986-11-05', 'Marketing', 48000),
(5, '1992-02-28', 'HR', 52000);
```

**Rename Table:**
```sql
ALTER TABLE emp_salary RENAME TO emp_info;
```

### d) Find the Sum of Salaries, Least, and Highest Salaries

**Sum of Salaries:**
```sql
SELECT SUM(salary) AS Total_Salaries FROM emp_info;
```

**Least Salary:**
```sql
SELECT MIN(salary) AS Least_Salary FROM emp_info;
```

**Highest Salary:**
```sql
SELECT MAX(salary) AS Highest_Salary FROM emp_info;
```

### e) List All Salaries in Ascending Order

```sql
SELECT salary FROM emp_info ORDER BY salary ASC;
```

### f) Create View and Syntax

**Create View:**

```sql
CREATE VIEW emp_summary AS
SELECT empcode, dept, salary
FROM emp_info;
```

**Syntax Explanation:**
- `CREATE VIEW` is used to create a view.
- `emp_summary` is the name of the view.
- The `SELECT` statement defines the query for the view, selecting `empcode`, `dept`, and `salary` from the `emp_info` table.

