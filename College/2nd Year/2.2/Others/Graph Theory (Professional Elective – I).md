### AM511PE: Graph Theory (Professional Elective – I)
#### B.Tech. III Year I Sem. L T P C
**3 0 0 3**

#### Course Objectives:
- **Understanding Graphs:** Introduction to graphs, trees, and their applications.
- **Exploring Applications:** Learning about the practical applications of trees and graphs.

#### Course Outcomes:
- **Classify Graph Problems:** Identify important classes of graph theoretic problems.
- **Prove Theorems:** Prove central theorems about trees, matching, connectivity, coloring, and planar graphs.
- **Apply Algorithms:** Describe and apply basic algorithms for graphs.
- **Model with Graph Theory:** Use graph theory as a modeling tool.

#### UNIT - I: Introduction to Graphs
- **Discovery of Graphs:** Historical context and basic definitions.
- **Subgraphs and Isomorphic Graphs:** Concept and identification.
- **Matrix Representations:** Adjacency matrix, incidence matrix.
- **Vertex Degree:** Definition and properties.
- **Walks, Paths, and Cycles:** Directed walks, paths, and cycles.
- **Connectivity:** In digraphs, Eulerian and Hamiltonian digraphs.
- **Special Graphs:** Complements, larger graphs from smaller ones.
- **Operations:** Union, Sum, Cartesian Product, Composition.
- **Graphic Sequences:** Havel-Hakimi criterion, realization of a graphic sequence.
- **Graph Theoretic Model:** Application to LAN problems.

#### UNIT - II: Connected Graphs and Shortest Paths
- **Walks, Trails, Paths, and Cycles:** Basic concepts and definitions.
- **Connected Graphs:** Definition and properties.
- **Distance:** Concept of distance in graphs.
- **Cut-Vertices and Cut-Edges:** Definitions and applications.
- **Blocks and Connectivity:** Basic concepts.
- **Weighted Graphs:** Concepts and algorithms.
- **Shortest Path Algorithms:**
  - **Dijkstra’s Algorithm:** Procedure and application.
  - **Floyd-Warshall Algorithm:** Procedure and application.

#### UNIT - III: Trees
- **Definitions and Characterizations:** Basic properties of trees.
- **Number of Trees:** Cayley’s formula.
- **Kirchhoff’s Matrix-Tree Theorem:** Introduction and application.
- **Minimum Spanning Trees:**
  - **Kruskal’s Algorithm:** Steps and application.
  - **Prim’s Algorithm:** Steps and application.
- **Special Classes of Graphs:**
  - **Bipartite Graphs:** Definitions and properties.
  - **Line Graphs:** Definitions and properties.
  - **Chordal Graphs:** Definitions and properties.
  - **Eulerian Graphs:** Fleury’s algorithm, Chinese Postman Problem.
  - **Hamilton Graphs:** Introduction, necessary and sufficient conditions.

#### UNIT - IV: Independent Sets, Coverings, and Matchings
- **Independent Sets and Coverings:** Basic equations and concepts.
- **Matchings in Bipartite Graphs:** Definitions and properties.
- **Hall’s Theorem:** Statement and proof.
- **König’s Theorem:** Statement and proof.
- **Perfect Matchings:** Definitions and properties.
- **Greedy and Approximation Algorithms:** Application and examples.

#### UNIT - V: Vertex and Edge Colorings
- **Vertex Colorings:**
  - **Basic Definitions:** Chromatic number, cliques.
  - **Mycielski’s Theorem:** Statement and proof.
  - **Greedy Coloring Algorithm:** Procedure and application.
  - **Coloring of Chordal Graphs:** Properties and algorithms.
  - **Brooks’ Theorem:** Statement and proof.
- **Edge Colorings:**
  - **Basics:** Definitions and concepts.
  - **Gupta-Vizing Theorem:** Statement and proof.
  - **Class-1 and Class-2 Graphs:** Definitions and properties.
  - **Edge-Coloring of Bipartite Graphs:** Definitions and properties.
  - **Class-2 Graphs:** Hajos union and equitable edge-coloring.

#### Text Books:
1. **J. A. Bondy and U. S. R. Murty,** *Graph Theory,* Graduate Texts in Mathematics, Springer, 1st edition, 2008.
2. **J. A. Bondy and U. S. R. Murty,** *Graph Theory with Applications.*

#### Reference Books:
1. **Lecture Videos:** [NPTEL Course on Graph Theory](http://nptel.ac.in/courses/111106050/13)
2. **Douglas B. West,** *Introduction to Graph Theory,* Pearson.### 01. Define the Term Degree Sequence of a Graph $G$

**Degree Sequence**: The degree sequence of a graph $G$ is a list of the degrees of all vertices in the graph, arranged in non-increasing order. The degree of a vertex is the number of edges incident to it.

**Example**: For a graph with vertices $v_1, v_2, v_3, v_4$ with degrees 3, 2, 2, and 1 respectively, the degree sequence is $(3, 2, 2, 1)$.

### 02. Define a Regular Graph with an Example

**Regular Graph**: A graph is called regular if every vertex has the same degree. 

**Example**: A 3-regular graph (also known as a cubic graph) is one where each vertex has exactly 3 edges. 

One example is the **complete graph $K_4$**, where each vertex is connected to every other vertex. In $K_4$, each vertex has a degree of 3, so it is a 3-regular graph.

### 03. Construct a Complete Bipartite Graph $K_{3,4}$

A **complete bipartite graph** $K_{m,n}$ is a graph where the vertex set can be partitioned into two disjoint sets of sizes $m$ and $n$, with every vertex in one set connected to every vertex in the other set.

**Construction**:
- Divide the vertex set into two subsets: $A$ with 3 vertices and $B$ with 4 vertices.
- Connect every vertex in $A$ to every vertex in $B$.

**Vertices**:
- Set $A = \{a_1, a_2, a_3\}$
- Set $B = \{b_1, b_2, b_3, b_4\}$

**Edges**:
- Connect each vertex in $A$ to each vertex in $B$: 
  $\{(a_1, b_1), (a_1, b_2), (a_1, b_3), (a_1, b_4), (a_2, b_1), (a_2, b_2), (a_2, b_3), (a_2, b_4), (a_3, b_1), (a_3, b_2), (a_3, b_3), (a_3, b_4)\}$

### 04. Define an Eulerian Trail with an Example

**Eulerian Trail**: An Eulerian trail (or path) in a graph is a trail that visits every edge exactly once. A graph has an Eulerian trail if and only if it is connected and has exactly zero or two vertices with an odd degree.

**Example**: The graph shown below has an Eulerian trail:
- Vertices: $\{A, B, C, D\}$
- Edges: $\{(A, B), (A, C), (B, C), (B, D), (C, D)\}$

  The Eulerian trail in this example could be: $A \to B \to D \to C \to B \to A \to C \to D$.

### 05. Construct a Directed Graph with 5 Vertices & 10 Edges

**Construction**:
- Use 5 vertices: $\{v_1, v_2, v_3, v_4, v_5\}$
- Add directed edges such that the total is 10.

**Example**:
- Edges: 
  $(v_1 \to v_2), (v_1 \to v_3), (v_2 \to v_3), (v_2 \to v_4), (v_3 \to v_4), (v_3 \to v_5), (v_4 \to v_5), (v_4 \to v_1), (v_5 \to v_1), (v_5 \to v_2)$

### 06. Define the Tree of a Graph $G$

**Tree of a Graph**: In graph theory, a **tree** is a connected acyclic graph. It has the following properties:
- There is exactly one path between any pair of vertices.
- A tree with $n$ vertices has $n-1$ edges.

**Constructing 2 Spanning Trees of a Complete Graph $K_4$**:

- **Spanning Tree 1**:
  $\text{Vertices: } \{1, 2, 3, 4\}$
  $\text{Edges: } \{(1, 2), (1, 3), (1, 4)\}$

- **Spanning Tree 2**:
  $\text{Vertices: } \{1, 2, 3, 4\}$
  $\text{Edges: } \{(1, 2), (2, 3), (3, 4)\}$

### 07. Define a Complete or Full Binary Tree with an Example

**Complete or Full Binary Tree**: A binary tree in which every node other than the leaves has exactly two children, and all levels except possibly the last are fully filled.

**Example**:
```
       1
     /   \
    2     3
   / \   / \
  4   5 6   7
```
In this example, every non-leaf node has exactly two children, and all levels are fully populated.

### 09. Define a Minimal Spanning Tree of a Graph $G$

**Minimal Spanning Tree (MST)**: A spanning tree of a weighted graph such that the total weight of the edges in the spanning tree is minimized. Every connected graph has at least one MST.

**Example**: For a weighted graph:
- **Vertices**: $\{A, B, C\}$
- **Edges**: $(A, B, 1), (A, C, 3), (B, C, 2)$

  An MST can be constructed using Kruskal’s or Prim’s algorithm.

### 10. State the Ideas of BFS & DFS Algorithms for Constructing Spanning Trees

**Breadth-First Search (BFS)**:
- Starts from a source vertex and explores all its neighbors at the current depth level before moving on to vertices at the next depth level.
- **Spanning Tree Construction**: The BFS algorithm constructs a spanning tree by adding edges to the tree as it explores the graph level by level from the starting vertex.

**Depth-First Search (DFS)**:
- Starts from a source vertex and explores as far as possible along each branch before backtracking.
- **Spanning Tree Construction**: The DFS algorithm constructs a spanning tree by adding edges to the tree as it explores each branch of the graph, diving deep into each path before backtracking.

