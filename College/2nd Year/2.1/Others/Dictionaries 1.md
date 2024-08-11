
# Dictionary

A dictionary is a general-purpose data structure designed for storing a group of objects. It is associated with a set of keys, and each key has a single associated value. When provided with a key, the dictionary returns the corresponding value. For instance, a classroom test results can be represented as a dictionary:

```python
results = {'Anik': 75, 'Aftab': 80, 'James': 85, 'Manisha': 77, 'Suhana': 87, 'Margaret': 82}
```

## Main Operations of Dictionaries

- **Retrieve a Value:** Based on the language, attempting to retrieve a missing key may provide a default value or throw an exception.
- **Inserting or Updating a Value:** If the key does not exist, a key-value pair is inserted; if the key already exists, its corresponding value is overwritten.
- **Remove or Delete a Key-Value Pair**
- **Test or Verify for Existence of a Key**

## Types of Representation

### 1. **Linear List**
   - Sorted linked list where linear traversal is required as skipping nodes during searching is not allowed.
![[Pasted image 20231120194704.png]]
### 2. **Skip List**
   - Utilizes multiple layers to enable skipping of nodes during search operations. An example is a list with 16 nodes and two layers, an "express lane" and a "normal lane."
![[Pasted image 20231120194711.png]]
#### Types of Skip List

1. **Perfect Skip List**
2. **Randomized Skip List**

In a perfect skip list, modifications to nodes at every level are required after insertion or deletion, making it a challenging task. Randomized skip lists offer a solution for these operations.
##### Perfect Skip Lists

A perfect skip list is a collection of lists at different levels. The structure of a perfect skip list is hierarchical, with each level forming a sorted, singly linked list of nodes. The levels are organized in a way that allows for efficient searching, insertion, and deletion operations.

**Structure**

- **Level 0 (Lowest Level):**
  - Represents a sorted, singly linked list of all nodes.

- **Level 1 (First Level):**
  - Links alternate nodes from the level 0 list.

- **Level 2 (Second Level):**
  - Links every fourth node from the level 0 list.

- **General Rule:**
  - At level i, every 2ᵗʰ node is linked.
  - In other words, level i links every 2^iᵗʰ node in the level 0 list.

- **Total Levels:**
  - There are [log₂ n] levels, where n is the number of nodes in the skip list.
  - This results in O(log n) levels.

- **Node Distribution:**
  - Each level has half the nodes of the one below it, resulting in a balanced structure.

 **Example**

Consider the following example where a perfect skip list is being constructed:
```
Level 2: 1---------------4-------------------10
Level 1: 1-------3-------4-------7-----------10
Level 0: 1---2---3---4---5---6---7---8---9---10
```
In this example, the lowest level (Level 0) forms a sorted linked list of all nodes. The higher levels link alternate or every 2ᵗʰ nodes, providing a skip mechanism that accelerates search operations.

**Advantages**

- **Solid and Trustworthy:**
  - Skip lists are reliable and provide a consistent structure.

- **Quick Insertion:**
  - Adding a new node is rapid and straightforward.

- **Ease of Implementation:**
  - Implementation is simpler compared to other data structures like hash tables and binary search trees.

- **Efficient Operations:**
  - Average-case time complexity for all operations is Θ(log n).

- **Straightforward Search:**
  - Locating a node in the list is relatively straightforward.



##### Randomized Skip List Searching

Searching an element is similar to the approach for searching a spot for inserting an element in the skip list. The basic idea involves:

1. If the key of the next node is less than the search key, move forward on the same level.
2. If the key of the next node is greater than the key to be inserted, store the pointer to the current node and move one level down to continue the search.
3. At the lowest level (0), if the element next to the rightmost element has a key equal to the search key, the key is found; otherwise, it's a failure.

### Example
Consider this example where we want to search for key 17.
![[Pasted image 20231120195506.png]]
# Skip List Operations

## Insertion

To insert a given key, the insertion process starts from the highest level, similar to the search operation. An example of inserting the key 17 is illustrated below:

### Example
Consider this example where we want to insert key 17.
![[Pasted image 20231120195517.png]]
## Deletion

Deletion of an element (k) involves locating the element in the skip list using the search algorithm mentioned earlier. Once the element is found, pointers are rearranged to remove the element, akin to a singly linked list. Deletion starts from the lowest level and continues until the element next to `update[i]` is not k. After deletion, there might be levels with no elements, so those levels are removed by decrementing the level of the skip list.

### Example
Consider this example where we want to delete element 6. At level 3, there is no element after deleting element 6, so the level of the skip list is decremented by 1.
![[Pasted image 20231120195523.png]]
## Advantages of Skip List

- The skip list is solid and trustworthy.
- Adding a new node is extremely quick.
- Easy to implement compared to hash tables and binary search trees.
- As the number of nodes increases, the likelihood of the worst-case scenario decreases.
- Requires only Θ(logn) time on average for all operations.
- Finding a node in the list is relatively straightforward.

## Disadvantages of Skip List

- Requires more memory than a balanced tree.
- Reverse search is not permitted.
- Searching is slower than a linked list.
- Skip lists are not cache-friendly as they don't optimize the locality of reference.

