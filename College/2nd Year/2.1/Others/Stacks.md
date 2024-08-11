### Stack:

A stack is a linear data structure that stores and manipulates data following the Last-In-First-Out (LIFO) order during the addition and removal of elements. There are two basic ways to implement a stack data structure:

1. **Array-based Implementation:**
   - In this implementation, a fixed-size array is used to create a stack.

2. **Linked List-based Implementation:**
   - In this implementation, a linked list is used to create a stack.

#### Array-based Implementation:

In array-based implementation, the stack is defined in terms of adding elements (Push) and removing elements (Pop). The stack allows insertions and deletions only at the top.

#### Stack Implementation using Array:

- **Initialization:**
  - Initialize an array `a[]` with size `n` to store stack elements.
  - Initialize an index `top` with -1 to represent an empty stack.

- **Push Operation:**
  - To add an element, increase the value of `top` by 1, and then push the new element at the position of `top`.

- **Pop Operation:**
  - To remove an element, first, pop the element at the position of `top`, and then decrease `top` by 1.

- **Points to be Aware of:**
  - **Fixed Capacity:**
    - A stack can hold a maximum of `n` elements, which is determined during initialization.
  - **Overflow:**
    - Once the stack reaches its maximum capacity, it is not possible to push any new element.
  - **Underflow:**
    - When no elements are left in the stack, it is not possible to pop elements from the stack.

#### Initialization:

- Initialize array `a[]` with size `n` to store stack elements.
- Initialize an index `top` with -1 to indicate that there are no elements in the stack.

## Operations
### Stack Operations Algorithms:

#### 1. Push Operation Algorithm:
```C
push(int data)
if stack is full
  print error message
else
  top = top + 1
  a[top] = data
```

#### 2. Pop Operation Algorithm:
```C
pop()
if stack is empty
  print error message
else
  print a[top]
  top = top - 1
```

#### 3. Traverse (Display) Operation Algorithm:
```C
display()
if stack is empty
  print error message
else
  print a[top] to a[0]
```

#### Auxiliary Stack Operations:

- **peek():**
```C
peek()
if stack is empty
  print error message
else
  return a[top]
```

- **size():**
```C
size()
return top + 1
```

- **isEmpty():**
```C
isEmpty()
return top == -1
```

- **isFull():**
```C
isFull()
return top == n - 1
```

### Stack Operations Dry Run:

To understand push and pop operations clearly, let's perform the following operations. Consider having a few balls and wanting to place or delete them on a request basis in a container (stack).

```C
push(10)
push(20)
push(30)
pop()
display()
```

Explanation:
- Push 10, 20, and 30 onto the stack.
- Pop an element (remove the last inserted element).
- Display the elements in the stack.

### Stack Operations – Example

#### Initialization:
- Let's consider the maximum capacity of the stack as 4.
- Initialize the top index as -1.

#### Push b1:
- Increment top by 1, so top now points at index 0.
- Store ball b1 at the top index, which is our last element.

#### Push b2:
- Increment top by 1, so top now is 1.
- Store ball b2 at the top position; b2 is now the last element in the stack.

#### Push b3:
- Increment top by 1, so top now is 2.
- Store ball b3 at the top position; b3 is the last element in the stack.

#### Push b4:
- Increment top by 1, so top now is 3.
- Store ball b4 at the top position; b4 is the last element in the stack.

#### Push b5:
- As the stack has reached its maximum capacity, adding a new element (b5) will result in overflow.

#### Pop:
- The top element b4 gets removed from the stack.
- The top index gets decremented by 1.

This example demonstrates the sequence of operations in a stack, including pushing elements, attempting to push beyond the capacity, and popping an element.
### Stack Auxiliary Operations:

#### 1. isFull() Operation:

This function checks if the stack is full or not. If the stack is full, then the insertion of elements is not possible, resulting in overflow error. The operation is performed as follows:

```plaintext
if (top == n-1)
  return 1
else
  return 0
```

#### 2. isEmpty() Operation:

This function validates if the stack is empty. If the top is equal to -1, then we can consider the stack as empty.

```plaintext
if (top == -1)
  return 1
else
  return 0
```

#### 3. Peek() Operation:

This function helps in extracting the data element where the top is pointing without removing it from the stack.

```plaintext
if (isEmpty())
  return "STACK IS EMPTY"
else
  return a[top]
```

These auxiliary operations are crucial for managing and verifying the state of the stack, whether it is full, empty, or to retrieve the top element without modification.



## Representations
### Stack Implementation using Linked List

The benefit of implementing a stack using a linked list over arrays is that it allows the stack to grow dynamically as needed.

#### **Node Structure:**

```c
struct Node {
    int data;
    struct Node *next;
};

struct Node *top = NULL;
```

#### **PUSH Operation:**

Adding or inserting a new element to a stack is known as the Push() operation in the stack. Elements can only be pushed at the top of the stack.

**Steps to push an element into a Stack:**

```c
// Create a new node (p) using dynamic memory allocation and assign value to the node.
struct Node *p = malloc(sizeof(struct Node));
p->data = value;

// Check if the stack is empty or not (if top == NULL).
// If it is empty, set the next pointer of the node to NULL.
// If it is not empty, link the newly created node to the current top element of the stack.
if (top == NULL)
    p->next = NULL;
else
    p->next = top;

// Make sure that the top of the stack always points to the newly created node.
top = p;
```

#### **POP Operation:**

Removing or deleting an element from a stack is known as the Pop() operation in the stack. Elements are popped from the top of the stack. There should be at least one element in the stack to perform the pop() operation.

**Steps to pop an element from a Stack:**

```c
// Check if the stack is empty or not (TOP == NULL).
// If it is empty, print Stack Underflow.
// If it is not empty, create a temporary node (t) and set it to top. 
// Print data of the temporary node (deleted element from the stack).
struct Node *t = top;
print t->data;

// Make top point to the next node.
top = top->next;

// Delete the temporary node.
free(t);
```


##### Function for Pop( ) :

```c
struct Node *t; // Declare a temporary pointer of type Node.

int pop( ) {
    if (top == NULL) { // Check if the stack is empty.
        printf("\nEMPTY STACK");
    } else {
        t = top; // Store the top node in the temporary pointer.
        printf("%d", top->data); // Print the data of the top node.
        top = top->next; // Update the top pointer to point to the next node.
        free(t); // Free the memory of the popped node.
    }
}
```



[[Stack Applications]]
![[Stack Applications]]