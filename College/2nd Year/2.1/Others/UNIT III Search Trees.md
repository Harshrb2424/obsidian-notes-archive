- Binary Search Trees

	- Definition
	- Implementation
	- Operations - Searching, Insertion, and Deletion

- B-Trees and B+ Trees

- AVL Trees

	- Definition
	- Height of an AVL Tree
	- Operations - Insertion, Deletion, and Searching

- Red–Black and Splay Trees
# Binary Search Trees
## Definition
  
A Binary Search Tree (BST) is a binary tree that meets the following conditions:

1. The data elements in the left subtree of any node are smaller than the node's own data.
2. The data elements equal to the node's data are in the right subtree.
3. Both the left and right subtrees of a node are also Binary Search Trees; they must also follow the aforementioned two rules.
## Implementation
## Operations - Searching, Insertion, and Deletion

This set of steps describes the search operation in a binary search tree (BST). The purpose is to find a specific element within the tree. Here's a summary in a clearer format:

1. **Search Operation in BST:**
   - **Step 1:** Read the search element from the user.
   - **Step 2:** Compare the search element with the value of the root node in the tree.
   - **Step 3:** If they match, display "Given node is found!!!" and terminate the function.
   - **Step 4:** If they don't match, check whether the search element is smaller or larger than that node's value.
   - **Step 5:** If the search element is smaller, continue the search process in the left subtree.
   - **Step 6:** If the search element is larger, continue the search process in the right subtree.
   - **Step 7:** Repeat the process until finding the exact element or until the search element is compared with the leaf node.
   - **Step 8:** If the node with a value equal to the search value is reached, display "Element is found" and terminate the function.
   - **Step 9:** If the leaf node is reached and it doesn't match the search element, display "Element is not found" and terminate the function.

The insertion operation in a binary search tree (BST) is designed to add a new node while maintaining the order of the tree. Here's a breakdown of the steps involved:

2. **Insertion Operation in BST:**
   - **Step 1:** Create a new node (newNode) with the given value and set its left and right pointers to NULL.
   - **Step 2:** Check whether the tree is empty.
   - **Step 3:** If the tree is empty, set the root to newNode.
   - **Step 4:** If the tree is not empty, compare the value of newNode with the value of the current node (starting from the root).
   - **Step 5:** If the value of newNode is smaller than or equal to the current node, move to its left child. If it's larger, move to its right child.
   - **Step 6:** Repeat the above steps until reaching a leaf node (i.e., a node with NULL left and right pointers).
   - **Step 7:** After reaching the leaf node, insert newNode as the left child if its value is smaller than or equal to the leaf node's value, or insert it as the right child if it's larger.

The deletion operation in a binary search tree (BST) involves three cases: deleting a leaf node, deleting a node with one child, and deleting a node with two children. Here's an explanation of each case:
3. **Deleting Operation in BST:**
**Case 1: Deleting a Leaf Node (A node with no children):**
   - **Step 1:** Find the node to be deleted using the search operation.
   - **Step 2:** Delete the node using the free function if it is a leaf (a node with no children) and terminate the function.

**Case 2: Deleting a Node with One Child:**
   - **Step 1:** Find the node to be deleted using the search operation.
   - **Step 2:** If the node has only one child, create a link between its parent node and child node.
   - **Step 3:** Delete the node using the free function and terminate the function.

**Case 3: Deleting a Node with Two Children:**
   - **Step 1:** Find the node to be deleted using the search operation.
   - **Step 2:** If the node has two children, find the largest node in its left subtree or the smallest node in its right subtree.
   - **Step 3:** Swap both the deleting node and the node found in the above step.
   - **Step 4:** Check whether the deleting node comes to case 1 or case 2; otherwise, go back to step 2.
   - **Step 5:** If it comes to case 1, delete using case 1 logic.
   - **Step 6:** If it comes to case 2, delete using case 2 logic.
   - **Step 7:** Repeat the same process until the node is deleted from the tree.


# B-Trees and B+ Trees
## B tree
- balanced m(order)-way tree.
- Generalization of BST in which a node can have more than one key and more than 2 children.
- Maintains sorted data.
- all leaf nodes must be at same level.
- B tree of order m has following properties:
	- Every node has maximum m children.
	- Minimum children 
		- leaf: 0
		- root: 2
		- Internal Node: m/2 (sealing)
- Every node has max. m-1 keys
- min key: 
	- root node: 1
	- all other nodes: (m/2)-1
# AVL Trees
(Easier to search)
All AVL are BST, All BST are BT.
BF = Balance Factor
it all the parents have BF of -1,0,1 are AVL tree.
## Definition
**AVL Tree Overview:**

1. **Introduction:**
   - AVL tree is a height-balanced binary search tree.
   - It's a specialized form of a binary search tree designed for optimal balance.

2. **Balanced Tree Concept:**
   - Binary trees are considered balanced if the height difference between left and right subtrees is -1, 0, or +1.
   - AVL trees enforce this balance condition, ensuring efficient search and retrieval.

3. **Balance Factor:**
   - Each node in an AVL tree maintains a balance factor.
   - Balance Factor (BF) = Height of Left Subtree - Height of Right Subtree (or vice versa).

4. **Introduction Year:**
   - Introduced in 1962 by G.M. Adelson-Velsky and E.M. Landis.

5. **Definition:**
   - AVL tree is defined as a balanced binary search tree where the balance factor of every node is -1, 0, or +1.

6. **Calculating Balance Factor:**
   - Balance factor calculated as heightOfLeftSubtree - heightOfRightSubtree.
   - Ensures adherence to AVL tree conditions.

7. **Binary Search Tree vs. AVL Tree:**
   - Every AVL tree is a binary search tree, but not every binary search tree qualifies as an AVL tree.
   - AVL trees impose stricter balance constraints.

8. **Maintaining Balance:**
   - AVL trees use rotations (single or double) to restore balance after insertions or deletions.
   - This ensures logarithmic height for optimized performance.

9. **Optimizing Operations:**
   - AVL trees offer O(log n) time complexity for common operations.
   - Height balancing enhances search, insertion, and deletion efficiency.

10. **Key Property:**
    - AVL trees prioritize maintaining logarithmic height, crucial for efficient operations.
### Create AVL tree
- RR Rotation
	- change the root node add to right side. (rotate the main root node anti clock wise)
- LL Rotation
	- change the root node add to left side. (rotate the main root node clock wise)
- RL Rotation
	- convert to RR Rotation by swoping (L) nodes.
- LR Rotation
	- convert to RL Rotation by swoping (R) nodes.

## Height of an AVL Tree
## Operations - Insertion, Deletion, and Searching
# Red–Black and Splay Trees