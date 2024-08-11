# 1.1 Explain in detail about red black tree with an example. **Unit 3 Pg 17**
![[Pasted image 20240130195716.png]]
![[Pasted image 20240130195750.png]]
# 1.2 What is a graph? Explain various representations of graphs.  **Unit 4 Pg 1**
![[Pasted image 20240130195929.png]]
#### Various representations of graphs **(Alternative in Pg )**
![[Pasted image 20240130200100.png]]
![[Pasted image 20240130203550.png]]![[Pasted image 20240130203558.png]]![[Pasted image 20240130203607.png]]
# 1.3 Explain BFS and DFS algorithm **Unit 4 Pg 11**
![[Pasted image 20240130200333.png]]
![[Pasted image 20240130200345.png]]
![[Pasted image 20240130202647.png]]![[Pasted image 20240130200356.png]]![[Pasted image 20240130200415.png]]![[Pasted image 20240130202715.png]]
# 1.4 Describe representation of graphs in Data structures **Unit 4 Pg 6**
![[Pasted image 20240130200530.png]]
![[Pasted image 20240130200606.png]]
![[Pasted image 20240130200623.png]]![[Pasted image 20240130200634.png]]
![[Pasted image 20240130200648.png]]
![[Pasted image 20240130200704.png]]
# 1.5 Write a note on TRIES  **Unit 5 Pg 14**
![[Pasted image 20240130200757.png]]![[Pasted image 20240130200814.png]]
![[Pasted image 20240130200844.png]]
# 1.6 Explain about Boyer-Moore algorithm in detail. **Unit 5 Pg 4**
![[Pasted image 20240130201440.png]]![[Pasted image 20240130201537.png]]![[Pasted image 20240130201549.png]]
![[Pasted image 20240130201616.png]]![[Pasted image 20240130201626.png]]![[Pasted image 20240130201634.png]]![[Pasted image 20240130201645.png]]![[Pasted image 20240130201659.png]]![[Pasted image 20240130201707.png]]

---
---

# 2.1 Write short note on splay tree rotations and with an example. **Unit 3 Pg 34/42**
![[Pasted image 20240130202209.png]]![[Pasted image 20240130202220.png]]![[Pasted image 20240130202348.png]]![[Pasted image 20240130202355.png]]
# 2.2 Implement Depth First Search (DFS) algorithm.  **Unit 4 Pg 11**
![[Pasted image 20240130200333.png]]
![[Pasted image 20240130200345.png]]
![[Pasted image 20240130202621.png]]
![[Pasted image 20240130202742.png]]![[Pasted image 20240130202755.png]]
# 2.3 Explain Adjacency matrix and Adjacency List **Unit 4 Pg 6**
![[Pasted image 20240130200530.png]]![[Pasted image 20240130200606.png]]
![[Pasted image 20240130200623.png]]![[Pasted image 20240130200634.png]]
# 2.4 What is Graph? Define any five types of graph. **Unit 4 Pg 1**

![[Pasted image 20240130195929.png]]
#### Types of graph
1. **Undirected Graph:**
   - Edges have no direction.
   - Connections between vertices are bidirectional.
   - If there's an edge from vertex A to vertex B, there's also an edge from B to A.
   
2. **Directed Graph (Digraph):**
   - Edges have a direction associated with them.
   - Relationships between vertices are one-way.
   - If there's a directed edge from vertex A to vertex B, there might not be a directed edge from B to A.
   ![700](https://miro.medium.com/v2/resize:fit:2000/1*HpYMnHjGZWmH9NKRG05lAg.jpeg)
3. **Weighted Graph:**
   - Each edge has an associated weight or cost.
   - Weights represent quantitative measures like distance, time, or cost.
   - Used to model scenarios where there's a quantitative measure associated with connections between vertices.
   ![500](https://miro.medium.com/v2/resize:fit:1344/1*ohvb5vhR7WRKbu1h2Du1kQ.png)
4. **Unweighted Graph:**
   - Edges have no associated weight.
   - All edges are considered equal.
   - Used when relationships between vertices are binary, without any quantitative measure.
![500](https://www.baeldung.com/wp-content/uploads/sites/4/2021/12/unweighted-example.jpg)
5. **Cyclic Graph and Acyclic Graph:**
   - **Cyclic Graph:**
     - Contains at least one cycle.
     - A cycle is a path that starts and ends at the same vertex.
     - You can traverse through the graph and return to the same starting point following a sequence of edges.
   - **Acyclic Graph:**
     - Does not contain any cycles.
     - Also known as a directed acyclic graph (DAG).
     - There's no way to traverse through the graph and return to the same starting point following a sequence of directed edges.
![700](https://i.imgur.com/2z9J2E5.png)
# 2.5 Write and explain Knuth-Morris-Pratt pattern matching algorithm. **Unit 5 Pg 10**
![[Pasted image 20240130203753.png]]
![[Pasted image 20240130204151.png]]![[Pasted image 20240130204205.png]]
### 4. Example:

text \( T \) and a pattern \( P \) as follows:

```
T: ABC ABCDAB ABCDABCDABDE
P: ABCDABD
```

1. Preprocessing (Building the Failure Function):

   - For the pattern \( P = "ABCDABD" \), the failure function would be:
     ```
     P:  A  B  C  D  A  B  D
     F:  0  0  0  0  1  2  0
     ```

2. Matching Algorithm:

   - We start comparing characters from the beginning of the text and the pattern.
   - When a mismatch occurs at position 7 in the pattern ("D" vs "B"), we consult the failure function.
   - The failure function tells us to shift the pattern by 2 characters to the right.
   - We continue comparing characters from the text and the shifted pattern.

3. Output:

   - The algorithm finds occurrences of the pattern \( P \) in the text \( T \) at positions 0 and 15.


# 2.6 Define TRIE. List and explain the types of tries. **Unit 5 Pg 14**
![[Pasted image 20240130200757.png]]![[Pasted image 20240130204718.png]]![[Pasted image 20240130204741.png]]
![[Pasted image 20240130204939.png]]