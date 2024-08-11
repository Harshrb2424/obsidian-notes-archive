**a) In the process of computerization of roadways travels , draw an ER diagram to design a database which consists database for buses, passengers, tickets, reservations and cancellation details.**
**b) Create table passenger with the following attributes(pnr_no, ticket_no,name, age, gender, category like AC or non AC)**
**c) insert 5 rows and rename passenger to passenger_info**
**d) display unique pnr numbers of all passengers.**
**e) list all the passengers whose age is greater than equal to 15years**
**f) Explain normalization and different forms of it**

### a) ER Diagram for Roadways Travels Database

The ER diagram for a roadways travel database would include entities such as Buses, Passengers, Tickets, Reservations, and Cancellations, along with their relationships.

**Entities and Attributes:**
- **Bus**: `Bus_ID`, `Bus_Number`, `Type` (AC or Non-AC), `Capacity`
- **Passenger**: `Passenger_ID`, `Name`, `Age`, `Gender`
- **Ticket**: `Ticket_No`, `Bus_ID`, `Passenger_ID`, `Reservation_ID`, `Cancellation_ID`
- **Reservation**: `Reservation_ID`, `Date`, `Time`
- **Cancellation**: `Cancellation_ID`, `Date`, `Time`

**Relationships:**
- A **Bus** has multiple **Tickets**.
- A **Passenger** can have multiple **Tickets**.
- A **Ticket** is associated with one **Reservation** and can optionally have a **Cancellation**.

**ER Diagram:**

![[Pasted image 20240722220324.png]]

### b) Create Table `passenger`

```sql
CREATE TABLE passenger (
    pnr_no INT PRIMARY KEY,
    ticket_no INT,
    name VARCHAR(100),
    age INT,
    gender CHAR(1),
    category VARCHAR(10)
);
```

### c) Insert 5 Rows and Rename Table to `passenger_info`

**Insert 5 Rows:**
```sql
INSERT INTO passenger (pnr_no, ticket_no, name, age, gender, category) VALUES
(1, 1001, 'John Doe', 25, 'M', 'AC'),
(2, 1002, 'Jane Smith', 30, 'F', 'Non-AC'),
(3, 1003, 'Sam Brown', 17, 'M', 'AC'),
(4, 1004, 'Nancy White', 45, 'F', 'Non-AC'),
(5, 1005, 'Mike Green', 12, 'M', 'AC');
```

**Rename Table:**
```sql
ALTER TABLE passenger RENAME TO passenger_info;
```

### d) Display Unique PNR Numbers of All Passengers

```sql
SELECT DISTINCT pnr_no FROM passenger_info;
```

### e) List All Passengers Whose Age is Greater Than or Equal to 15 Years

```sql
SELECT * FROM passenger_info WHERE age >= 15;
```

### f) Explain Normalization and Different Forms of It

**Normalization** is the process of organizing data in a database to reduce redundancy and improve data integrity. The main goals are to:
1. Eliminate redundant data.
2. Ensure data dependencies make sense.

**Forms of Normalization:**

1. **First Normal Form (1NF):**
   - Ensure that the table has a primary key.
   - Eliminate repeating groups (each column contains atomic values, no multiple values in a single column).

   **Example:**
   ```sql
   CREATE TABLE students (
       student_id INT PRIMARY KEY,
       name VARCHAR(100),
       subjects VARCHAR(100)  -- Violates 1NF if it stores multiple subjects like "Math, Science"
   );
   ```

   **1NF Example:**
   ```sql
   CREATE TABLE students (
       student_id INT PRIMARY KEY,
       name VARCHAR(100)
   );
   CREATE TABLE student_subjects (
       student_id INT,
       subject VARCHAR(100),
       FOREIGN KEY (student_id) REFERENCES students(student_id)
   );
   ```

2. **Second Normal Form (2NF):**
   - Ensure that the table is in 1NF.
   - Remove partial dependencies (all non-key attributes should depend on the whole primary key).

   **Example:**
   ```sql
   CREATE TABLE orders (
       order_id INT,
       product_id INT,
       product_name VARCHAR(100),  -- Partial dependency on product_id
       quantity INT,
       PRIMARY KEY (order_id, product_id)
   );
   ```

   **2NF Example:**
   ```sql
   CREATE TABLE orders (
       order_id INT,
       product_id INT,
       quantity INT,
       PRIMARY KEY (order_id, product_id)
   );
   CREATE TABLE products (
       product_id INT PRIMARY KEY,
       product_name VARCHAR(100)
   );
   ```

3. **Third Normal Form (3NF):**
   - Ensure that the table is in 2NF.
   - Remove transitive dependencies (non-key attributes should depend only on the primary key).

   **Example:**
   ```sql
   CREATE TABLE employee (
       emp_id INT PRIMARY KEY,
       emp_name VARCHAR(100),
       dept_id INT,
       dept_name VARCHAR(100)  -- Transitive dependency on dept_id
   );
   ```

   **3NF Example:**
   ```sql
   CREATE TABLE employee (
       emp_id INT PRIMARY KEY,
       emp_name VARCHAR(100),
       dept_id INT
   );
   CREATE TABLE department (
       dept_id INT PRIMARY KEY,
       dept_name VARCHAR(100)
   );
   ```

