**a)  In the process of computerization of roadways travels , draw an ER diagram to design a database which consists database for buses, passengers, tickets, reservations and cancellation details.**
**b) create a table bus with the following attributes (bus no, source, destination, weekday);**
**c) insert 5 rows and rename bus to buses**
**d) display source which starts with ‘M’**
**e)select all bus numbers which run in between Monday to wednesday**
**f) write about cursors and explain it with a syntax for creating it.**

### a) ER Diagram for Roadways Travels Database

**Entities and Attributes:**
- **Bus**: `Bus_No`, `Source`, `Destination`, `Weekday`
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

### b) Create Table `bus`

```sql
CREATE TABLE bus (
    bus_no INT PRIMARY KEY,
    source VARCHAR(100),
    destination VARCHAR(100),
    weekday VARCHAR(20)
);
```

### c) Insert 5 Rows and Rename Table to `buses`

**Insert 5 Rows:**
```sql
INSERT INTO bus (bus_no, source, destination, weekday) VALUES
(1, 'Mumbai', 'Pune', 'Monday'),
(2, 'Mumbai', 'Goa', 'Tuesday'),
(3, 'Delhi', 'Agra', 'Wednesday'),
(4, 'Chennai', 'Bangalore', 'Thursday'),
(5, 'Mumbai', 'Delhi', 'Friday');
```

**Rename Table:**
```sql
ALTER TABLE bus RENAME TO buses;
```

### d) Display Source which Starts with ‘M’

```sql
SELECT source FROM buses WHERE source LIKE 'M%';
```

### e) Select All Bus Numbers Which Run Between Monday to Wednesday

```sql
SELECT bus_no FROM buses WHERE weekday IN ('Monday', 'Tuesday', 'Wednesday');
```

### f) Cursors in SQL

**Cursors** are database objects used to retrieve, manipulate, and navigate through a result set row by row. They are particularly useful when you need to process each row individually.

**Types of Cursors:**
1. **Implicit Cursor**: Automatically created by SQL when a single row is fetched.
2. **Explicit Cursor**: Defined and controlled by the user for processing multiple rows.

**Syntax for Creating an Explicit Cursor:**

1. **Declare Cursor**: Define the cursor and its SQL query.
2. **Open Cursor**: Allocate resources for the cursor and execute the query.
3. **Fetch Cursor**: Retrieve rows from the cursor one at a time.
4. **Close Cursor**: Release resources associated with the cursor.

**Example:**

```sql
DECLARE
    CURSOR bus_cursor IS
        SELECT bus_no, source, destination FROM buses WHERE weekday IN ('Monday', 'Tuesday', 'Wednesday');
    
    bus_record buses%ROWTYPE;  -- Variable to hold each row fetched from the cursor

BEGIN
    OPEN bus_cursor;  -- Open the cursor
    
    LOOP
        FETCH bus_cursor INTO bus_record;  -- Fetch each row into bus_record
        
        EXIT WHEN bus_cursor%NOTFOUND;  -- Exit loop if no more rows are found
        
        -- Process each row (example: display bus_no)
        DBMS_OUTPUT.PUT_LINE('Bus No: ' || bus_record.bus_no || ', Source: ' || bus_record.source || ', Destination: ' || bus_record.destination);
    END LOOP;
    
    CLOSE bus_cursor;  -- Close the cursor
END;
```

**Explanation:**
- **DECLARE**: Declares the cursor `bus_cursor` with a SQL query to select bus details for specific weekdays.
- **bus_record**: A variable of type `buses%ROWTYPE` to hold each fetched row.
- **BEGIN...END**: Block to execute cursor operations.
- **OPEN bus_cursor**: Opens the cursor and executes the query.
- **LOOP...FETCH...EXIT**: Loop to fetch rows from the cursor into `bus_record` and process them. The loop exits when no more rows are found.
- **CLOSE bus_cursor**: Closes the cursor to release resources.

