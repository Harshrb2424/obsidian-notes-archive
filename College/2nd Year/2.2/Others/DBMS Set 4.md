**a) In the process of computerization in colleges , draw an ER diagram to design a database which consists database for student, staff, departments, and administration details.**
**b) create the following tables: Student (roll_no, marks, category, district, state) and Student_rank(roll_no, marks, rank)**
**c)insert 5 rows into each table**
**d)  list all those students who have come from ‘Telangana’ state and secured  a rank above 100**
**e)select all the fields from students where state is ‘AP’ or ‘UP’.**
**f) write a procedure and show the syntax to create it**

### a) ER Diagram for College Database

**Entities and Attributes:**
- **Student**: `Student_ID`, `Name`, `DOB`, `Dept_ID`
- **Staff**: `Staff_ID`, `Name`, `DOB`, `Dept_ID`
- **Department**: `Dept_ID`, `Dept_Name`, `Head_ID` (Staff_ID as foreign key)
- **Administration**: `Admin_ID`, `Name`, `Role`

**Relationships:**
- A **Department** has multiple **Students**.
- A **Department** has multiple **Staff** members.
- A **Staff** member can be the head of a **Department**.
- An **Administration** oversees multiple **Departments**.

**ER Diagram:**

![[Pasted image 20240722220853.png]]

### b) Create Tables

```sql
CREATE TABLE Student (
    roll_no INT PRIMARY KEY,
    marks INT,
    category VARCHAR(50),
    district VARCHAR(50),
    state VARCHAR(50)
);

CREATE TABLE Student_rank (
    roll_no INT PRIMARY KEY,
    marks INT,
    rank INT,
    FOREIGN KEY (roll_no) REFERENCES Student(roll_no)
);
```

### c) Insert 5 Rows into Each Table

```sql
INSERT INTO Student (roll_no, marks, category, district, state) VALUES
(1, 85, 'General', 'Hyderabad', 'Telangana'),
(2, 92, 'OBC', 'Warangal', 'Telangana'),
(3, 78, 'SC', 'Vijayawada', 'AP'),
(4, 88, 'General', 'Lucknow', 'UP'),
(5, 80, 'ST', 'Guntur', 'AP');

INSERT INTO Student_rank (roll_no, marks, rank) VALUES
(1, 85, 120),
(2, 92, 50),
(3, 78, 200),
(4, 88, 90),
(5, 80, 150);
```

### d) List All Those Students Who Have Come from ‘Telangana’ State and Secured a Rank Above 100

```sql
SELECT s.roll_no, s.marks, s.category, s.district, s.state, sr.rank
FROM Student s
JOIN Student_rank sr ON s.roll_no = sr.roll_no
WHERE s.state = 'Telangana' AND sr.rank > 100;
```

### e) Select All the Fields from Students Where State is ‘AP’ or ‘UP’

```sql
SELECT * FROM Student
WHERE state IN ('AP', 'UP');
```

### f) Write a Procedure and Show the Syntax to Create It

**Procedure Example:**

Let's create a procedure to update the marks of a student based on their roll number.

**Procedure Syntax:**

```sql
DELIMITER //

CREATE PROCEDURE UpdateStudentMarks (
    IN student_roll_no INT,
    IN new_marks INT
)
BEGIN
    UPDATE Student
    SET marks = new_marks
    WHERE roll_no = student_roll_no;
END //

DELIMITER ;
```

**Explanation:**
- `DELIMITER //`: Changes the delimiter to allow the procedure definition to contain semicolons.
- `CREATE PROCEDURE UpdateStudentMarks`: Defines a new procedure named `UpdateStudentMarks`.
- `IN student_roll_no INT, IN new_marks INT`: Defines two input parameters, `student_roll_no` and `new_marks`.
- `BEGIN ... END`: Block containing the SQL statements to execute.
- `UPDATE Student SET marks = new_marks WHERE roll_no = student_roll_no;`: Updates the `marks` column in the `Student` table for the given `roll_no`.
- `DELIMITER ;`: Resets the delimiter back to the default semicolon.

To call the procedure:
```sql
CALL UpdateStudentMarks(1, 95);
```

