# 1. **a) Explain the difference between linear data structures and non linear data structures.**
   **b) Explain in detail about double linked list.**
## a)
![[Linear List 1#Difference between Linear and Non-linear Data Structures]]


## b)
![[Linked List 1#Doubly Linked List]]
# 2. **a) Write a program to implement stack operations**
   **b) What are the applications of Queues ? Explain.**
   a) 
   ![[Stacks#Operations#Stack Operations Algorithms]]
b)
![[Queues#**Queue **]]
![[Queues#Applications of Queue]]
# 3. **What is single linked list write an algorithm for insertion, deletion and search operations using single linked list.**
   ![[Linked List 1#Singly Linked List]]
# 4. **Define and explain in detail about Binary search tree. Explain insertion operation using one example.**
   ![[Pasted image 20231124203447.png]]![[Pasted image 20231124203459.png]]![[Pasted image 20231124203534.png]]![[Pasted image 20231124203545.png]]
# 5. **Explain the operations of skip list representation.**
   ![[Dictionaries 1#Skip List Operations]]
# 6. **Is linear probing and Open addressing same ? Justify your answer.**
   **Open Addressing:**
- A generic term for a method dealing with collisions in hash tables.
- When a collision occurs (two keys hash to the same index), the algorithm looks for the next available slot in the hash table.
- Includes various techniques for finding the next available slot, such as linear probing, quadratic probing, and double hashing.

**Linear Probing:**
- A specific form of open addressing.
- When a collision occurs, linear probing searches for the next available slot by probing consecutively in a linear fashion.
- If the slot at the hashed index is occupied, it checks the next slot, then the next, and so on, until it finds an empty slot.

Hence, Linear probing is a type of open addressing.
Not all open addressing techniques involve linear probing; others include quadratic probing, double hashing, etc.
Linear probing is one strategy within the broader category of open addressing.

# 7. **a) What is hashing? Discuss the hash function.**
   **b) List and explain Advantages of extendable hashing.**
a) ![[Hash Table Representation 1#Hashing]]
![[Hash Table Representation 1#Hash Functions]]

b)
advantages of extendable hashing:

1. **Dynamic Size Adjustment:**
   - Adjusts hash table size dynamically based on the number of keys.
2. **No Fixed Size Limit:**
   - Grows or shrinks dynamically, adapting to changing workloads.
3. **Efficient Space Utilization:**
   - Compact representation reduces wasted space and memory overhead.
4. **Balanced Load Distribution:**
   - Maintains balanced distribution of keys, preventing excessive collisions.
5. **Minimal Reorganization:**
   - Requires only partial bucket splits or merges during resizing.
6. **Support for Incremental Growth:**
   - Allows gradual expansion or contraction in response to key changes.
7. **Low Overhead for Updates:**
   - Fast insertions and deletions with minimal bucket modifications.
8. **Query Efficiency:**
   - Balanced load and controlled bucket size contribute to uniform access time.

# 8. **a) Write down the differences between STACK and QUEUE.**
   **b) Distinguish between Linked list and skip list.**
   a) The differences between a Stack and a Queue:

| Characteristic                     | Stack                                             | Queue                                      |
|------------------------------------|----------------------------------------------------|--------------------------------------------|
| **Order of Elements**               | Last In, First Out (LIFO)                          | First In, First Out (FIFO)                 |
| **Insertion Operation**             | 1. **Push:** Adds an element to the top of the stack. | 1. **Enqueue:** Adds an element to the rear of the queue.   |
| **Deletion Operation**              | 2. **Pop:** Removes the element from the top of the stack. | 2. **Dequeue:** Removes the element from the front of the queue. |
| **Access**                         | Limited to the top element.                         | Limited to the front element.               |
| **Additional Operations**          | 3. **Peek/Top:** View the top element without removing it. | 3. **Front:** View the front element without removing it. |
| **Real-world Analogy**             | Pile of plates or books, where you can only add or remove from the top. | Line of people waiting in a queue, where the first person to join is the first to be served. |
| **Usage**                         | Function call management (call stack), undo mechanisms, expression evaluation. | Task scheduling, print spooling, breadth-first search algorithms. |


   b) distinguishing between Linked Lists and Skip Lists:

| Characteristic                     | Linked List                                      | Skip List                                       |
|------------------------------------|--------------------------------------------------|-------------------------------------------------|
| **Basic Structure**                 | - Linear collection of nodes where each node has a data field and a reference (pointer) to the next node.   | - Multiple layers of linked lists, where each layer is a separate linked list. Nodes on higher levels have references to nodes on lower levels. |
| **Search Operation**               | - O(n) in the worst case, as you may need to traverse the list sequentially.                                   | - O(log n) on average. The multiple layers allow for "skipping" ahead in the structure, similar to a binary search. Uses probabilistic balancing to maintain logarithmic height. |
| **Insertion and Deletion**         | - Efficient for insertions and deletions at any position, as these operations involve updating pointers.         | - Efficient (O(log n)) for insertions and deletions. Balancing ensures logarithmic height and maintains overall structure integrity. |
| **Memory Usage**                   | - Can be memory-efficient, as nodes only need to store data and a single reference.                               | - May use more memory due to the additional structure of multiple layers. The trade-off is made for faster search times. |

- **Balancing:** Skip lists achieve logarithmic search times through probabilistic balancing. This means that the structure maintains balance on average, but individual instances may differ.

- **Randomization:** Skip lists use a degree of randomization to determine the height of each node, contributing to their efficient performance.

- **Adaptability:** Skip lists adapt well to dynamic datasets, where insertions and deletions are frequent, maintaining efficient search times.

- **Complexity:** While skip lists offer better average-case search times compared to linked lists, they are more complex to implement and may require additional bookkeeping for maintaining their structure.

# 9. **Explain double hashing? Explain the insertion operation with example.**
   ![[Hash Table Representation 1#2.c) Double Hashing]]
# 10. **a) Explain about load factor in hashing.**
**b) What is collision? Explain in detail about collision.**
a)
## Load Factor in Hashing

The load factor of a hash table is a crucial metric that indicates the relationship between the number of items stored in the hash table and its size. It is calculated by dividing the number of items in the hash table by the total size of the hash table. The load factor becomes particularly significant when considering whether to rehash a previous hash function or when adding more elements to an existing hash table.

### Importance of Load Factor:

1. **Efficiency of the Hash Function**
2. **Rehashing Decision**
3. **Dynamic Sizing**

### Load Factor Formula:

The load factor (LF) is calculated using the formula:

$\text{Load Factor (LF)} = \frac{\text{Number of Items}}{\text{Size of Hash Table}}$

Where:
- **Number of Items:** The current count of elements stored in the hash table.
- **Size of Hash Table:** The total capacity or size of the hash table.

- **Low Load Factor (LF < 1):**
  - Indicates that the hash table has ample space relative to the number of items.
  - Hash collisions may be less frequent, resulting in better performance.

- **High Load Factor (LF > 1):**
  - Suggests that the hash table is becoming crowded.
  - Increased likelihood of hash collisions, potentially leading to performance degradation.
  - May trigger rehashing to maintain efficiency.

b)
## Collision

In hashing, the process of generating a small number for a large key may lead to the possibility of two keys producing the same value. This situation is known as a collision, and various techniques are used to handle it.
![[Pasted image 20231120195639.png]]
### Collision Resolution

There are two main methods to handle collisions:


![[Pasted image 20231120195645.png]]


1. **Chaining Collisions:**
   - In chaining, each slot in the hash table is the head of a linked list. When a collision occurs, the collided keys are added to the linked list at that slot.
   - Chaining provides a simple and effective way to handle collisions. It allows multiple keys with the same hash value to coexist at the same index by forming a linked list of collided keys.
   - **Advantages:**
     - No limit on the number of elements with the same hash value.
     - Simple to implement.
   - **Disadvantages:**
     - Memory overhead due to the storage of linked lists.
     - Cache inefficiency as elements are scattered in memory.

2. **Open Addressing Collisions:**
   - In open addressing, when a collision occurs, the algorithm looks for the next available slot in the hash table to place the collided key.
   - Various techniques exist within open addressing, including linear probing, quadratic probing, and double hashing. These methods determine the sequence in which the algorithm searches for the next available slot.
   - **Advantages:**
     - No additional memory overhead for linked lists.
     - Better cache performance as elements are stored contiguously.
   - **Disadvantages:**
     - Can lead to clustering, where consecutive slots are occupied, increasing the likelihood of more collisions.
     - Difficulty in finding an efficient probing sequence.

**Collision Resolution:**
- **Separate Chaining:** In chaining collisions, the hash table slots contain linked lists to handle multiple elements with the same hash value.
- **Linear Probing:** In open addressing collisions, the algorithm looks for the next available slot in a linear sequence.
- **Quadratic Probing:** The algorithm uses a quadratic function to determine the next slot in open addressing collisions.
- **Double Hashing:** Another hash function determines the step size for probing in open addressing.

