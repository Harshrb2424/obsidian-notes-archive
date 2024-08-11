### 01. Prove that $A \cap (B - A) = \emptyset$

**Proof:**

1. **Definition of Difference**: $B - A$ is the set of elements that are in $B$ but not in $A$.
2. **Intersection with $A$**: For any element $x \in A \cap (B - A)$, $x$ must be in both $A$ and $B - A$.
3. **Contradiction**: By definition, $x \in B - A$ means $x \notin A$. Therefore, $x$ cannot be in $A$ and $B - A$ at the same time.
4. **Conclusion**: Hence, $A \cap (B - A) = \emptyset$.

### 02. Compute $P - Q$, $P \cup Q$, and $P + Q$ where $P = \{3a, 2b, 1c\}$ and $Q = \{4a, 3b, 2d\}$

1. **Difference $P - Q$**:
   $P - Q = \{x \in P \mid x \notin Q\} = \{3a, 1c\}$

2. **Union $P \cup Q$**:
   $P \cup Q = \{3a, 2b, 1c\} \cup \{4a, 3b, 2d\} = \{1c, 2b, 2d, 3b, 3a, 4a\}$

3. **Sum $P + Q$**: Assuming "sum" means the union (since the typical set operations don’t include a direct “sum”):
   $P + Q = P \cup Q = \{1c, 2b, 2d, 3b, 3a, 4a\}$

### 03. Determine the number of students who failed in both papers

1. **Given**: 
   - Total students = 900
   - Passed in paper I = 740
   - Passed in paper II = 660
   - Passed in both papers = 640

2. **Using the principle of inclusion-exclusion**:
   $\text{Passed in at least one paper} = (\text{Passed in I}) + (\text{Passed in II}) - (\text{Passed in both}) $
   $\text{Passed in at least one paper} = 740 + 660 - 640 = 760$
   $\text{Failed in both} = \text{Total students} - \text{Passed in at least one paper} = 900 - 760 = 140$

### 04. Compute $R \circ S$ where $A = \{1, 2, 3\}$, $B = \{p, q, r\}$, $C = \{x, y, z\}$, $R = \{(1, p), (1, r), (2, q), (3, q)\}$, and $S = \{(p, y), (q, x), (r, z)\}$

1. **Composition $R \circ S$**: For $(a, c) \in R \circ S$, there should be an intermediate $b$ such that $(a, b) \in R$ and $(b, c) \in S$.

   - For $(1, p) \in R$ and $(p, y) \in S$: \((1, y)\)
   - For $(1, r) \in R$ and $(r, z) \in S$: \((1, z)\)
   - For $(2, q) \in R$ and $(q, x) \in S$: \((2, x)\)
   - For $(3, q) \in R$ and $(q, x) \in S$: \((3, x)\)

   Thus,
   $R \circ S = \{(1, y), (1, z), (2, x), (3, x)\}$

### 05. Compute the transitive closure of $R = \{(1, 2), (2, 1), (2, 3), (3, 4), (4, 1)\}$ on $A = \{1, 2, 3, 4\}$ using Warshall's Algorithm

1. **Initial Matrix $M$**:
   $M = \begin{bmatrix}
   0 & 1 & 0 & 0 \\
   1 & 0 & 1 & 0 \\
   0 & 0 & 0 & 1 \\
   1 & 0 & 0 & 0
   \end{bmatrix}$

2. **Warshall's Algorithm**: 
   - Update matrix for each intermediate vertex $k$ where $k$ ranges from 1 to 4.
   - For example, if updating for $k = 1$, check if $M[i, j]$ can be updated to true by checking if $M[i, k]$ and $M[k, j]$ are true.

   After completing Warshall’s Algorithm, the transitive closure matrix will be:
   $M_{tc} = \begin{bmatrix}
   1 & 1 & 1 & 1 \\
   1 & 1 & 1 & 1 \\
   1 & 1 & 1 & 1 \\
   1 & 1 & 1 & 1
   \end{bmatrix}$

### 06. Write matrices for relations and prove $(M_{R} * M_{S})^C = M_{R}^C * M_{S}^C$

1. **Matrix for Relation $R$**: $R = \{(x, y) \mid x + y = 3\}$
   $M_R = \begin{bmatrix}
   0 & 1 & 1 & 0 \\
   1 & 0 & 0 & 1 \\
   1 & 0 & 0 & 1 \\
   0 & 1 & 1 & 0
   \end{bmatrix}$

2. **Matrix for Relation $S$**: $S = \{(x, y) \mid x + y \leq 4\}$
   $M_S = \begin{bmatrix}
   1 & 1 & 1 & 1 \\
   1 & 1 & 1 & 1 \\
   1 & 1 & 1 & 0 \\
   1 & 1 & 0 & 0
   \end{bmatrix}$

3. **Complement Relations**:
   $M_{R}^C = \text{Complement of } M_R$
   $M_{S}^C = \text{Complement of } M_S$
   Verify that:
   $(M_R * M_S)^C = M_R^C * M_S^C$

### 07. Compute $f \circ g$ and $g \circ f$ where $f(x) = (x^2 - 2)$ and $g(x) = x + 4$

1. **Composition $f \circ g$**:
   $(f \circ g)(x) = f(g(x)) = f(x + 4) = ((x + 4)^2 - 2) = x^2 + 8x + 16 - 2 = x^2 + 8x + 14$

2. **Composition $g \circ f$**:
   $(g \circ f)(x) = g(f(x)) = g(x^2 - 2) = (x^2 - 2) + 4 = x^2 + 2$

### 08. Prove that $f(x) = 7x + 10$ is invertible and compute $f^{-1}$

1. **Invertibility**: 
   - $f(x) = 7x + 10$ is a linear function with a non-zero slope (7), hence it is invertible.

2. **Inverse Function**:
   $y = 7x + 10$
   $x = \frac{y - 10}{7}$
   $f^{-1}(y) = \frac{y - 10}{7}$

### 09 & 10. Construct the Hasse diagrams and determine glb (greatest lower bound) and lub (least upper bound)

1. **Positive Divisors**:

   - **

For 36**: $\{1, 2, 3, 4, 6, 9, 12, 18, 36\}$
   - **For 120**: $\{1, 2, 3, 4, 5, 6, 8, 10, 12, 15, 20, 24, 30, 40, 60, 120\}$

2. **Hasse Diagram**: Construct the diagrams by drawing edges from lower to higher elements based on divisibility.

3. **glb & lub**:
   - **For \(\{6, 18\}\)**: glb = 6, lub = 18
   - **For \(\{4, 6, 9\}\)**: glb = 1, lub = 36

