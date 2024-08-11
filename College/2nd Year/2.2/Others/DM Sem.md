# Unit 1
### **1. Introduction to Mathematical Logic**

Mathematical logic is a branch of mathematics that deals with formal systems and symbolic reasoning. It encompasses various areas, including propositional logic, predicate logic, and proof theory.

### **2. Statements and Notation**

- **Statements**: Sentences that are either true or false but not both. Examples: "It is raining" or "2 + 2 = 4."

- **Notation**:
  - **Propositions**: Represented by variables like $p, q, r$.
  - **Logical Connectives**:
    - **Negation**: $\neg p$ (not p)
    - **Conjunction**: $p \land q$ (p and q)
    - **Disjunction**: $p \lor q$ (p or q)
    - **Implication**: $p \rightarrow q$ (if p then q)
    - **Biconditional**: $p \leftrightarrow q$ (p if and only if q)

| $p$ | $q$ | $\neg p$ | $p \land q$ | $p \lor q$ | $p \rightarrow q$ | $p \leftrightarrow q$ |
|--------|--------|-------------|----------------|---------------|-----------------------|--------------------------|
|   T    |   T    |      F      |       T        |       T       |           T           |            T             |
|   T    |   F    |      F      |       F        |       T       |           F           |            F             |
|   F    |   T    |      T      |       F        |       T       |           T           |            F             |
|   F    |   F    |      T      |       F        |       F       |           T           |            T             |

### **3. Connectives**

- **Negation** ($\neg$): Inverts the truth value. $\neg p$ is true if $p$ is false.
- **Conjunction** ($\land$): True if both operands are true. $p \land q$ is true if both $p$ and $q$ are true.
- **Disjunction** ($\lor$): True if at least one operand is true. $p \lor q$ is true if either $p$, $q$, or both are true.
- **Implication** ($\rightarrow$): $p \rightarrow q$ is false only if $p$ is true and $q$ is false; otherwise, it is true.
- **Biconditional** ($\leftrightarrow$): $p \leftrightarrow q$ is true if both $p$ and $q$ have the same truth value (both true or both false).

### Laws:


| **Law**                                          | **Formula**                                             |
| ------------------------------------------------ | ------------------------------------------------------- |
| **Identity Laws**                                |                                                         |
| Disjunction with False                           | $p \lor \text{False} = p$                           |
| Conjunction with True                            | $p \land \text{True} = p$                           |
| **Domination Laws**                              |                                                         |
| Disjunction with True                            | $p \lor \text{True} = \text{True}$                  |
| Conjunction with False                           | $p \land \text{False} = \text{False}$               |
| **Idempotent Laws**                              |                                                         |
| Disjunction Idempotence                          | $p \lor p = p$                                      |
| Conjunction Idempotence                          | $p \land p = p$                                     |
| **Complement Laws**                              |                                                         |
| Disjunction with Complement                      | $p \lor \neg p = \text{True}$                       |
| Conjunction with Complement                      | $p \land \neg p = \text{False}$                     |
| **Double Negation Law**                          |                                                         |
| Double Negation                                  | $\neg(\neg p) = p$                                  |
| **De Morgan's Laws**                             |                                                         |
| De Morgan’s Disjunction                          | $\neg (p \lor q) = \neg p \land \neg q$             |
| De Morgan’s Conjunction                          | $\neg (p \land q) = \neg p \lor \neg q$             |
| **Distributive Laws**                            |                                                         |
| Distributive Law of Conjunction over Disjunction | $p \land (q \lor r) = (p \land q) \lor (p \land r)$ |
| Distributive Law of Disjunction over Conjunction | $p \lor (q \land r) = (p \lor q) \land (p \lor r)$  |
| **Absorption Laws**                              |                                                         |
| Absorption of Disjunction                        | $p \lor (p \land q) = p$                            |
| Absorption of Conjunction                        | $p \land (p \lor q) = p$                            |
| **Associative Laws**                             |                                                         |
| Associativity of Disjunction                     | $(p \lor q) \lor r = p \lor (q \lor r)$             |
| Associativity of Conjunction                     | $(p \land q) \land r = p \land (q \land r)$         |
| **Commutative Laws**                             |                                                         |
| Commutativity of Disjunction                     | $p \lor q = q \lor p$                               |
| Commutativity of Conjunction                     | $p \land q = q \land p$                             |


### **4. Normal Forms**

- **Conjunctive Normal Form (CNF)**: A conjunction of clauses, where each clause is a disjunction of literals. Example: $(p \lor q) \land (\neg p \lor r)$
- **Disjunctive Normal Form (DNF)**: A disjunction of terms, where each term is a conjunction of literals. Example: $(p \land \neg q) \lor (r \land s)$

**Conversion to Normal Forms**:

- **CNF Conversion**: Apply rules like distribution and De Morgan’s laws to express a formula as a conjunction of disjunctions.
- **DNF Conversion**: Apply distributive laws to express a formula as a disjunction of conjunctions.

| **Term**                                     | **Example**                                                                    |
| -------------------------------------------- | ------------------------------------------------------------------------------ |
| **PCNF** (Principal Conjunctive Normal Form) | $(p \lor q) \land (\neg p \lor r)$                                           |
| **PDNF** (Principal Disjunctive Normal Form) | $(p \land \neg q) \lor (r \land s)$                                          |
| **Minterms**                                 | $p \land q$, $p \land \neg q$, $\neg p \land q$, $\neg p \land \neg q$ |
| **Maxterms**                                 | $p \lor q$, $p \lor \neg q$, $\neg p \lor q$, $\neg p \lor \neg q$     |
- **PCNF**: Principal Conjunctive Normal Form is a normalized CNF where no redundant literals are included in the clauses.
- **PDNF**: Principal Disjunctive Normal Form is a normalized DNF where no redundant terms are included in the disjunction.
- **Minterms**: Complete conjunctions of literals that make the function true, used in the canonical representation of Boolean functions.
- **Maxterms**: Complete disjunctions of literals that make the function false, used in the canonical representation of Boolean functions.

### **5. Theory of Inference for the Statement Calculus**

- **Inference Rules**: Methods to derive conclusions from premises.

  - **Modus Ponens**: From $p \rightarrow q$ and $p$, infer $q$.
  - **Modus Tollens**: From $p \rightarrow q$ and $\neg q$, infer $\neg p$.
  - **Disjunctive Syllogism**: From $p \lor q$ and $\neg p$, infer $q$.
  - **Hypothetical Syllogism**: From $p \rightarrow q$ and $q \rightarrow r$, infer $p \rightarrow r$.

- **Proof Techniques**:
  - **Direct Proof**: Demonstrate the truth of a statement by logical reasoning.
  - **Indirect Proof**: Assume the negation of the statement and derive a contradiction.
  - **Proof by Contradiction**: Assume the statement is false and show this leads to a contradiction.
  - **Proof by Cases**: Divide the problem into cases and prove each one.

### **6. The Predicate Calculus**

- **Predicates**: Functions that return true or false based on input values. Example: $P(x)$ where $P$ is a predicate and $x$ is a variable.

- **Quantifiers**:

  - **Universal Quantifier** ($\forall$): Indicates that the statement holds for all elements in the domain. Example: $\forall x (P(x))$ means "for all $x$, $P(x)$ is true."
  - **Existential Quantifier** ($\exists$): Indicates that there is at least one element in the domain for which the statement holds. Example: $\exists x (P(x))$ means "there exists an $x$ such that $P(x)$ is true."

- **Forms**:

| Statement Type              | Original Statement                       | Negation Formula                         |
| --------------------------- | ---------------------------------------- | ---------------------------------------- |
| **Universal Statement**     | $\forall x (P(x) \rightarrow Q(x))$      | $\exists x \neg (P(x) \rightarrow Q(x))$ |
| **Negation of Universal**   | $\neg \forall x (P(x) \rightarrow Q(x))$ | $\exists x \neg (P(x) \rightarrow Q(x))$ |
| **Existential Statement**   | $\exists x (P(x) \land Q(x))$            | $\forall x \neg (P(x) \land Q(x))$       |
| **Negation of Existential** | $\neg \exists x (P(x) \land Q(x))$       | $\forall x \neg (P(x) \land Q(x))$       |


### **7. Inference Theory of the Predicate Calculus**

- **Rules of Inference for Predicate Logic**:

  - **Universal Instantiation**: From $\forall x \, P(x)$, infer $P(a)$ for a specific $a$.
  - **Universal Generalization**: From $P(a)$ for an arbitrary $a$, infer $\forall x \, P(x)$.
  - **Existential Instantiation**: From $\exists x \, P(x)$, infer $P(a)$ for some specific $a$.
  - **Existential Generalization**: From $P(a)$ for a specific $a$, infer $\exists x \, P(x)$.

- **Proof Techniques**:
  - **Direct Proof**: Construct a proof using logical steps and inference rules.
  - **Proof by Contradiction**: Assume the negation and derive a contradiction using predicates and quantifiers.
# Unit 2
### 1. Introduction to Set Theory

**Set theory** is a branch of mathematical logic that studies sets, which are collections of objects. It forms the basis for several areas of mathematics, providing a foundation for defining and working with mathematical structures and concepts.

**Basic Definitions:**
- **Set:** A collection of distinct objects, considered as an object in its own right. For example, the set of natural numbers $\{1, 2, 3, \ldots\}$.
- **Element:** An object that is a member of a set. If $x$ is an element of a set $A$, we write $x \in A$.
- **Subset:** A set $B$ is a subset of $A$ if all elements of $B$ are also elements of $A$. We write $B \subseteq A$.
- **Empty Set:** The set that contains no elements, denoted by $\emptyset$ or $\{\}$.
- **Universal Set:** The set that contains all objects under consideration for a particular discussion or problem.

### 2. Basic Concepts of Set Theory

**Basic Operations:**
- **Union ($\cup$):** The union of sets $A$ and $B$ is the set of elements that are in $A$, in $B$, or in both. 
  $A \cup B = \{x \mid x \in A \text{ or } x \in B\}$

- **Intersection ($\cap$):** The intersection of sets $A$ and $B$ is the set of elements that are in both $A$ and $B$.
  $A \cap B = \{x \mid x \in A \text{ and } x \in B\}$

- **Difference ($-$):** The difference between sets $A$ and $B$ is the set of elements that are in $A$ but not in $B$.
  $A - B = \{x \mid x \in A \text{ and } x \notin B\}$

- **Complement:** The complement of a set $A$ with respect to a universal set $U$ is the set of elements in $U$ that are not in $A$.
  $A^c = U - A$

**Properties:**
- **Associative:** $(A \cup B) \cup C = A \cup (B \cup C)$, and $(A \cap B) \cap C = A \cap (B \cap C)$.
- **Commutative:** $A \cup B = B \cup A$, and $A \cap B = B \cap A$.
- **Distributive:** $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$, and $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$.

### 3. Representation of Discrete Structures

**1. Set Notation:**
- **Roster Notation:** Listing all elements explicitly, e.g., $A = \{1, 2, 3\}$.
- **Set-builder Notation:** Describing the properties that its members must satisfy, e.g., $B = \{x \mid x \text{ is an even number}\}$.

**2. Venn Diagrams:**
- Visual representations of sets and their relationships, showing intersections, unions, and differences.

**3. Matrix Representation:**
- For finite sets, relations can be represented by matrices where the cell (i, j) indicates the presence or absence of a relation between elements $i$ and $j$.

### 4. Relations and Ordering

**1. Relation:**
- A relation $R$ from set $A$ to set $B$ is a subset of the Cartesian product $A \times B$. It defines a relationship between elements of $A$ and $B$.
  $R \subseteq A \times B$

**2. Types of Relations:**
- **Reflexive:** Every element is related to itself. $\forall a \in A, (a, a) \in R$.
- **Symmetric:** If $(a, b) \in R$, then $(b, a) \in R$.
- **Transitive:** If $(a, b) \in R$ and $(b, c) \in R$, then $(a, c) \in R$.
- **Antisymmetric:** If $(a, b) \in R$ and $(b, a) \in R$, then $a = b$.

**3. Partial Ordering:**
- A relation that is reflexive, antisymmetric, and transitive. It provides a way to compare elements of a set, such as less than or equal to ($\leq$).

**4. Total Ordering:**
- A partial order where any two elements are comparable. For every $a$ and $b$ in the set, either $a \leq b$ or $b \leq a$.

### 5. Functions

**1. Function:**
- A function $f$ from set $A$ to set $B$ assigns exactly one element of $B$ to each element of $A$. Denoted $f: A \to B$.

**2. Types of Functions:**
- **Injective (One-to-One):** Different elements in $A$ map to different elements in $B$.
- **Surjective (Onto):** Every element in $B$ is mapped to by at least one element in $A$.
- **Bijective:** A function that is both injective and surjective. It establishes a one-to-one correspondence between $A$ and $B$.

**3. Function Composition:**
- If $f: A \to B$ and $g: B \to C$, then the composition $g \circ f$ is a function from $A$ to $C$ where $(g \circ f)(x) = g(f(x))$.

**4. Inverse Function:**
- If $f: A \to B$ is bijective, the inverse function $f^{-1}: B \to A$ exists such that $f^{-1}(f(x)) = x$ for all $x \in A$ and $f(f^{-1}(y)) = y$ for all $y \in B$.

