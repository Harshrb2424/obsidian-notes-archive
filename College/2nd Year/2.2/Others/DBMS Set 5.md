**a) In the process of computerization of roadways travels , draw an ER diagram to design a database which consists database for buses, passengers, tickets, reservations and cancellation details.**
**b) Create table ticket with the following attributes(ticket_no, ticket_price ,age,gender,source, arrival_time, dept_time)**
**c) insert 5 rows and rename ticket to ticket_info**
**d) display all the names of female passengers.**
**e) list  all the tickets that are priced higher than the average**
**f) write and create a syntax for triggers with an example**.

### a) ER Diagram for Roadways Travels Database

**Entities and Attributes:**
- **Bus**: `Bus_ID`, `Bus_Number`, `Type` (AC or Non-AC), `Capacity`
- **Passenger**: `Passenger_ID`, `Name`, `Age`, `Gender`
- **Ticket**: `Ticket_No`, `Ticket_Price`, `Age`, `Gender`, `Source`, `Arrival_Time`, `Dept_Time`
- **Reservation**: `Reservation_ID`, `Date`, `Time`
- **Cancellation**: `Cancellation_ID`, `Date`, `Time`

**Relationships:**
- A **Bus** has multiple **Tickets**.
- A **Passenger** can have multiple **Tickets**.
- A **Ticket** is associated with one **Reservation** and can optionally have a **Cancellation**.

**ER Diagram:**

![[Pasted image 20240722220324.png]]
### b) Create Table `ticket`

```sql
CREATE TABLE ticket (
    ticket_no INT PRIMARY KEY,
    ticket_price DECIMAL(10, 2),
    age INT,
    gender CHAR(1),
    source VARCHAR(100),
    arrival_time TIME,
    dept_time TIME
);
```

### c) Insert 5 Rows and Rename Table to `ticket_info`

**Insert 5 Rows:**
```sql
INSERT INTO ticket (ticket_no, ticket_price, age, gender, source, arrival_time, dept_time) VALUES
(1, 150.00, 25, 'M', 'CityA', '10:00', '12:00'),
(2, 200.00, 30, 'F', 'CityB', '11:00', '13:00'),
(3, 175.00, 20, 'F', 'CityC', '12:00', '14:00'),
(4, 180.00, 45, 'M', 'CityD', '13:00', '15:00'),
(5, 160.00, 35, 'F', 'CityE', '14:00', '16:00');
```

**Rename Table:**
```sql
ALTER TABLE ticket RENAME TO ticket_info;
```

### d) Display All the Names of Female Passengers

**Create and Populate Passenger Table:**
First, create the `passenger` table and populate it to relate passengers to tickets.

```sql
CREATE TABLE passenger (
    passenger_id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    gender CHAR(1),
    ticket_no INT,
    FOREIGN KEY (ticket_no) REFERENCES ticket_info(ticket_no)
);

INSERT INTO passenger (passenger_id, name, age, gender, ticket_no) VALUES
(1, 'Alice', 30, 'F', 2),
(2, 'Bella', 20, 'F', 3),
(3, 'Charlie', 45, 'M', 4),
(4, 'Diana', 35, 'F', 5),
(5, 'Edward', 25, 'M', 1);
```

**Display Names:**
```sql
SELECT name FROM passenger WHERE gender = 'F';
```

### e) List All the Tickets That Are Priced Higher Than the Average

**Calculate Average Price and List Higher Priced Tickets:**
```sql
SELECT * FROM ticket_info 
WHERE ticket_price > (SELECT AVG(ticket_price) FROM ticket_info);
```

### f) Create and Explain Syntax for Triggers

**Syntax for Creating Triggers:**
Triggers are used to automatically perform actions based on certain events in the database. Here's a basic example of creating an `AFTER INSERT` trigger.

**Example Trigger:**

Let's create a trigger that logs any new ticket inserted into a log table called `ticket_log`.

**Create Log Table:**
```sql
CREATE TABLE ticket_log (
    log_id INT AUTO_INCREMENT PRIMARY KEY,
    ticket_no INT,
    action VARCHAR(50),
    log_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

**Create Trigger:**
```sql
DELIMITER //
CREATE TRIGGER after_ticket_insert
AFTER INSERT ON ticket_info
FOR EACH ROW
BEGIN
    INSERT INTO ticket_log (ticket_no, action) VALUES (NEW.ticket_no, 'INSERTED');
END;
//
DELIMITER ;
```

**Explanation:**
- `DELIMITER //`: Changes the delimiter so we can define the trigger without interfering with semicolons in the trigger body.
- `CREATE TRIGGER after_ticket_insert AFTER INSERT ON ticket_info FOR EACH ROW`: Defines a trigger named `after_ticket_insert` that activates after an insert operation on the `ticket_info` table.
- `BEGIN ... END;`: Defines the trigger body. In this case, it inserts a log entry into the `ticket_log` table with the `ticket_no` and action 'INSERTED'.
- `DELIMITER ;`: Resets the delimiter back to the default semicolon.

