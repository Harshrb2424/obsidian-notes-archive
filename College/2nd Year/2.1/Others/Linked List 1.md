# Singly Linked List

A singly linked list is a data structure comprising nodes, each containing data and a pointer to the address of the next node in the list. The size of linked list elements is not fixed, allowing for efficient memory utilization.

#### Node Declaration:
```c
struct node
{
  int data;
  struct node *next;
};
```

## Insertion Operations:

1. **Insertion at the Beginning:**
   - The new node is added before the head of the linked list, becoming the new head.
   - Steps:
     1. Allocate a new node.
     2. Assign data to the new node.
     3. Set the next of the new node as the current head.
     4. Move the head to point to the new node.

   ```c
   void insert_begin(struct node *head, int data)
   {
     struct node *p = malloc(sizeof(struct node));
     p->data = data;
     p->next = head;
     head = p;
   }
   ```

2. **Insertion After a Given Node:**
   - A new node is inserted after the given node.
   - Steps:
     1. Allocate a new node.
     2. Assign data to the new node.
     3. Find the given previous node in the list.
     4. Set the next of the new node as the next of the given previous node.
     5. Update the next of the previous node to the new node.

   ```c
   void insertAfter(struct node *head, int data, int x)
   {
     struct node *p = malloc(sizeof(struct node));
     p->data = data;
     struct node *t = head;
     while (x != t->data)
       t = t->next;
     p->next = t->next;
     t->next = p;
   }
   ```

3. **Insertion at the End:**
   - The new node is added after the last node in the linked list.
   - Steps:
     1. Allocate a new node.
     2. Assign data to the new node.
     3. Traverse the list to the last node.
     4. Set the next of the last node to the new node.

   ```c
   void insert_end(struct node *head, int data)
   {
     struct node *p = malloc(sizeof(struct node));
     p->data = data;
     p->next = NULL;
     struct node *t = head;
     while (t->next != NULL)
       t = t->next;
     t->next = p;
   }
   ```

Understanding these insertion operations is fundamental for manipulating singly linked lists efficiently.


## Delete from a Linked List:

Nodes in a linked list can be deleted in three ways: at the beginning, at the end, or at a specified position in the middle.

#### Delete at Beginning:

To delete a node at the beginning, update the head to point to the next node and free the memory of the removed node.

```c
void del_begin(struct node *head)
{
  struct node *t = head;
  head = head->next;
  free(t);
}
```

#### Delete at End:

To delete a node at the end, find the last second element, change its `next` pointer to `NULL`, and free the memory of the removed node.

```c
void del_end(struct node *head)
{
  struct node *t = head;
  struct node *p;
  while (t->next != NULL)
  {
    p = t;
    t = t->next;
  }
  if (t == head)
    head = NULL;
  else
    p->next = NULL;
  free(t);
}
```

#### Delete a Given Node:

To delete a node at a specified position, keep track of the pointer (`p`) before the node to delete and the pointer (`t`) to the node to delete. Update the `next` pointer of the previous node or the `head` if the first node is deleted, and free the memory of the removed node.

```c
void del(struct node *head, int x)
{
  struct node *t = head;
  struct node *p;
  while (x != t->data)
  {
    p = t;
    t = t->next;
  }
  if (t == head)
    head = head->next;
  else
    p->next = t->next;
  free(t);
}
```





## Displaying a Singly Linked List:

To display the elements of a singly linked list, you can follow these steps:

1. **Check whether the list is Empty:**
   - If `head == NULL`, display "List is Empty!!!" and terminate the function.

2. **If Not Empty:**
   - Define a Node pointer `temp` and initialize it with `head`.

3. **Display Elements:**
   - Keep displaying `temp → data` with an arrow (`--->`) until `temp` reaches `NULL`.

```c
t = head;
while (t != NULL)
{
  printf("%d-->", t->data);
  t = t->next;
}
printf("NULL\n");
```

## Applications of Singly Linked List:

1. **Implementing Stacks and Queues:**
   - Fundamental data structures in computer science.

2. **Collision Prevention in Hash Maps:**
   - Singly linked lists are used to handle collisions in hash maps.

3. **Notepad Functions:**
   - Casual notepad applications use singly linked lists for undo, redo, and deleting functions.

4. **Photo Viewer in Slide Show:**
   - Singly linked lists can be used in a photo viewer for continuous slideshow functionality.

5. **Train System:**
   - Analogous to a singly linked list, the system of adding a new train bogie involves either adding it at the end or finding a spot in between bogies to insert.

Understanding these applications showcases the versatility and usefulness of singly linked lists in various scenarios.

# Doubly Linked List:

A doubly linked list is a more complex type of linked list where each node, in addition to storing its data, has two links. The first link points to the previous node in the list, and the second link points to the next node in the list.

| Prev | Data | Next |
|------|------|------|

```C
/// Structure of Doubly Linked List
struct Node {
    struct Node* prev;
    int data;
    struct Node* next;
};
```

![[Pasted image 20231124193438.png]]

- `head`: The first node in the list.
- `Prev`: Pointer to the previous node in the sequence.
- `Data`: Actual data or payload stored in the node.
- `Next`: Pointer to the next node in the sequence.

### Operations on a Doubly Linked List include:

1. **Insertion:** Insert a node at the beginning, end, or in the middle of the list.
2. **Deletion:** Delete a node from the beginning, end, or in the middle of the list.
3. **Traversal:** Traverse the list in either direction.
4. **Search:** Search for a specific element in the list.
### Applications of Doubly Linked List:

1. **Browser Navigation:**
   - In web browsers, the back or next function to change tabs utilizes the concept of a doubly-linked list.

2. **Implementation of Other Data Structures:**
   - Doubly linked lists are easily used to implement other data structures like binary trees, hash tables, stacks, etc.

3. **Music Playing System:**
   - In music playing systems, a doubly linked list allows easy navigation between the previous and next songs.

4. **Thread Scheduler in Operating Systems:**
   - Many operating systems use a doubly-linked list in the thread scheduler to maintain a list of all processes running. This facilitates easy movement of a process from one queue to another.

5. **Deck of Cards in Games:**
   - The concept of a doubly linked list is used in games, particularly in representing a deck of cards.

# Circular Linked List:

A circular linked list forms a circular structure where the first node points to its next node, and the last node points to the first head node, creating a circular arrangement. Both singly and doubly linked lists can be transformed into circular linked lists.

### Applications of Circular Linked List:

1. **Implementation of Queues:**
   - Circular linked lists are used to implement queues by maintaining a pointer to the last inserted node, and the front can always be obtained as the next of the last node.

2. **Advanced Data Structures:**
   - Circular doubly linked lists are used for the implementation of advanced data structures like Fibonacci Heap. The reference to the previous node can be easily found in this structure.

3. **Operating System Time Sharing:**
   - Operating systems use circular linked lists to share time for different users, employing a Round-Robin time-sharing mechanism. This ensures that each user gets an equal share of system resources in turns.

4. **Multiplayer Games:**
   - Circular lists are used in multiplayer games to swap between players in a loop, providing a fair and continuous gaming experience.

5. **Graphics and Editing Software:**
   - Applications like Photoshop, Word, or any paint software use the circular linked list concept in the undo function. It allows users to revert changes in a cyclic manner.

# Advantages of Linked Lists over Arrays:

1. **Dynamic Memory Allocation:**
   - Linked lists allow dynamic memory allocation, enabling flexibility in size.

2. **Ease of Insertion/Deletion:**
   - Inserting and deleting elements in linked lists is more straightforward compared to arrays.

# Drawbacks of Linked Lists:

1. **No Random Access:**
   - Sequential access is required; random access is not allowed.

2. **Extra Memory for Pointers:**
   - Each element in the list requires additional memory for a pointer.

3. **Not Cache-Friendly:**
   - Lack of locality of reference as in arrays, affecting cache efficiency.

# Types of Linked Lists:

1. **Singly Linked List:**
   - Traversal is possible only in one direction.

2. **Doubly Linked List:**
   - Traversal is possible in both forward and backward directions.

3. **Circular Linked List:**
   - Last node links to the first/head node, forming a circular structure.

# [[Operations on Linear List 1]]
![[Operations on Linear List 1]]