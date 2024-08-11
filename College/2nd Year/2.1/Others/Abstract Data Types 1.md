### **Abstract Data Types (ADT)**

1. **Introduction to Data Types:**
   - In-built data types include int, float, double, long, etc.
   - Basic operations like addition, subtraction, multiplication, and division can be performed on these types.

2. **Need for User-defined Data Types:**
   - Situations may arise where operations on user-defined data types are required.
   - Operations on user-defined types must be defined as needed.

3. **Abstract Data Types (ADT) Defined:**
   - ADT is a type or class for objects.
   - Behavior is defined by a set of values and a set of operations.
   - Only outlines what operations are to be performed, not how they are implemented.
   - It provides an implementation-independent view, abstracting away details of memory organization and algorithm implementations.

4. **Abstraction in ADT:**
   - Abstraction is the process of providing only essentials and hiding details.
   - Users do not need to know the implementation details of a data type.
   - ADT is considered "abstract" because it hides inner structures, giving a high-level view.

5. **User Interaction with ADT:**
   - Users only need to know what operations a data type can perform, not how they are implemented.
   - ADT is like a black box, concealing the internal workings of the data type.

6. **Examples of ADTs:**
   - Three examples of ADTs are List ADT, Stack ADT, and Queue ADT.
   - These ADTs define operations that can be performed on lists, stacks, and queues without specifying how these operations are implemented.

7. **Implementation Independence:**
   - ADT emphasizes the separation of what operations are to be done from how they are done.
   - Users can focus on utilizing the data type without concern for its internal workings.

8. **Summary of ADT in Exam Context:**
   - ADT is a crucial concept for handling user-defined data types.
   - It offers an abstraction layer, allowing users to interact without knowing the internal details.
   - Examples such as List ADT, Stack ADT, and Queue ADT illustrate how operations can be defined without specifying implementation details.
   - Understanding ADTs is vital for effective problem-solving, emphasizing a clear separation between what operations are performed and how they are implemented.

### **List ADT:**

1. **Data Organization:**
   - Data is stored in key sequence in a list.
   - Each data node contains a pointer to a data structure and a self-referential pointer to the next node.

2. **List ADT Functions:**
   - `get()`: Returns an element from the list at a specified position.
   - `insert()`: Inserts an element at any position in the list.
   - `remove()`: Removes the first occurrence of any element from a non-empty list.
   - `removeAt()`: Removes the element at a specified location from a non-empty list.
   - `replace()`: Replaces an element at any position with another element.
   - `size()`: Returns the number of elements in the list.
   - `isEmpty()`: Returns true if the list is empty, false otherwise.
   - `isFull()`: Returns true if the list is full, false otherwise.

### **Stack ADT:**

1. **Implementation:**
   - Data is not stored in each node; instead, the pointer to data is stored.
   - Memory for data is allocated, and the address is passed to the stack ADT.
   - Encapsulation of head node and data nodes; calling functions only see the pointer to the stack.

2. **Stack ADT Functions:**
   - `push()`: Inserts an element at the top of the stack.
   - `pop()`: Removes and returns the element at the top of the stack if it's not empty.
   - `peek()`: Returns the element at the top of the stack without removing it if the stack is not empty.
   - `size()`: Returns the number of elements in the stack.
   - `isEmpty()`: Returns true if the stack is empty, false otherwise.
   - `isFull()`: Returns true if the stack is full, false otherwise.

### **Queue ADT:**

1. **Data Structure Design:**
   - Similar to the stack ADT, with each node containing a void pointer to data and a link pointer to the next element.

2. **Queue ADT Functions:**
   - `enqueue()`: Inserts an element at the end of the queue.
   - `dequeue()`: Removes and returns the first element of the queue if it's not empty.
   - `peek()`: Returns the element at the front of the queue without removing it if the queue is not empty.
   - `size()`: Returns the number of elements in the queue.
   - `isEmpty()`: Returns true if the queue is empty, false otherwise.
   - `isFull()`: Returns true if the queue is full, false otherwise.

### **Features of ADT:**

1. **Abstraction:**
   - Users don't need to know the implementation details of the data structure.

2. **Better Conceptualization:**
   - ADT provides a conceptualization of real-world scenarios.

3. **Robustness:**
   - The program is robust and can catch errors.

### **Implementation Flexibility:**

1. **Implementation Variety:**
   - Different ways to implement ADTs (e.g., List ADT using arrays, singly linked lists, or doubly linked lists).

2. **ADT Flexibility:**
   - Stack ADT and Queue ADT can be implemented using arrays or linked lists.
