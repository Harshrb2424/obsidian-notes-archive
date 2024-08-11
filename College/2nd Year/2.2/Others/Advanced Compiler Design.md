# Syntax-Directed Translation

## Syntax-Directed Definitions (SDD)

**Definition:**
Syntax-Directed Definitions specify the values of attributes by associating semantic rules with grammar productions. They are a formal method to attach semantics to the syntactic structure of a programming language.

**Components:**
1. **Attributes:** Each grammar symbol is associated with attributes.
   - **Synthesized Attributes:** These are computed from the attribute values of the children nodes.
   - **Inherited Attributes:** These are computed from the attribute values of the parent and/or sibling nodes.

2. **Semantic Rules:** These are rules that define how to compute the attribute values.

**Example:**
Consider a simple grammar for arithmetic expressions:
```
E → E1 + T
E → T
T → T1 * F
T → F
F → ( E )
F → id
```

A possible SDD could be:
- Attributes: `E.val`, `T.val`, `F.val`
- Semantic Rules:
  ```
  E → E1 + T  { E.val = E1.val + T.val }
  E → T       { E.val = T.val }
  T → T1 * F  { T.val = T1.val * F.val }
  T → F       { T.val = F.val }
  F → ( E )   { F.val = E.val }
  F → id      { F.val = id.lexval }
  ```

## Evaluation Orders for SDD's

**Definition:**
The order in which the semantic rules are evaluated to compute the attributes is called the evaluation order.

**Types:**
1. **Dependency Graph:** This is a directed graph where nodes represent attributes, and edges represent dependencies between attributes. 

2. **Topological Sort:** A linear ordering of vertices of a directed graph such that for every directed edge `uv`, vertex `u` comes before `v`. This helps in determining a valid evaluation order.

**Methods:**
- **Bottom-Up Evaluation:** Suitable for synthesized attributes.
- **Top-Down Evaluation:** Suitable for inherited attributes.
- **Mixed Approach:** Combining both top-down and bottom-up evaluations as needed.

## Syntax-Directed Translation Schemes (SDTS)

**Definition:**
Syntax-Directed Translation Schemes are extensions of syntax-directed definitions where semantic actions are embedded within the production rules of the grammar. These actions are executed during parsing.

**Components:**
- **Grammar Productions:** Define the syntactic structure.
- **Embedded Actions:** These are code snippets written in the host language that are executed when the production is applied.

**Example:**
For the arithmetic expression grammar:
```
E → E1 + T  { print('+') }
E → T
T → T1 * F  { print('*') }
T → F
F → ( E )
F → id      { print(id.lexval) }
```

## Implementing L-Attributed SDD's

**Definition:**
L-Attributed SDD's are a subclass of SDD's where each attribute is either synthesized or inherited in such a way that the dependencies form a directed acyclic graph with certain restrictions.

**Properties:**
- Each synthesized attribute is computed from the attributes of the children.
- Each inherited attribute is computed from the attributes of the parent and/or the attributes of the siblings to the left.

**Implementation Steps:**
1. **Attribute Grammar:** Define the attributes and the semantic rules.
2. **Annotated Parse Tree:** Construct a parse tree and annotate it with attribute values.
3. **Order of Evaluation:** Use topological sort to determine a valid order of evaluation.

**Example:**
For the following grammar with attributes:
```
E → T { E.val = T.val }
T → T1 * F { T.val = T1.val * F.val }
T → F { T.val = F.val }
F → ( E ) { F.val = E.val }
F → id { F.val = id.lexval }
```
The L-attributed rules ensure that `T.val` and `F.val` are computed correctly as per the dependencies.

# Intermediate-Code Generation

## Variants of Syntax Trees

### Abstract Syntax Trees (ASTs)

**Definition:**
An Abstract Syntax Tree (AST) is a simplified, tree-like representation of the abstract syntactic structure of source code. Each node of the tree denotes a construct occurring in the source code.

**Characteristics:**
- **Abstraction:** ASTs abstract away unnecessary syntactic details.
- **Nodes:** Represent constructs like expressions, statements, declarations, etc.
- **Edges:** Represent the syntactic relationships between these constructs.

**Example:**
Consider the expression `a + b * c`:
```
      +
     / \
    a   *
       / \
      b   c
```

### Directed Acyclic Graphs (DAGs)

**Definition:**
A Directed Acyclic Graph (DAG) is a variant of syntax trees where common sub-expressions are shared to avoid redundancy.

**Characteristics:**
- **Nodes:** Represent expressions or sub-expressions.
- **Edges:** Represent dependencies between these expressions.
- **Acyclic:** No cycles, representing the hierarchical structure of the expression.

**Example:**
For the expression `a + a * b + b * c`, the DAG would be:
```
      +
     / \
    +   *
   /|   |\
  a *   b c
   /\
  a  b
```

### Control Flow Graphs (CFGs)

**Definition:**
A Control Flow Graph (CFG) represents the flow of control in a program. Nodes represent basic blocks (a sequence of statements with a single entry and exit point), and edges represent control flow between these blocks.

**Characteristics:**
- **Nodes:** Basic blocks.
- **Edges:** Control flow paths.

**Example:**
For a simple if-else statement:
```c
if (x < 0)
    x = -x;
else
    x = x + 1;
```
The CFG would be:
```
      [entry]
         |
    [if x < 0]
     /        \
[ x = -x]   [ x = x + 1]
     \        /
      [exit]
```

## Three-Address Code (TAC)

**Definition:**
Three-Address Code (TAC) is an intermediate code used in compilers that simplifies code generation and optimization. Each instruction in TAC typically contains at most three addresses (two operands and one result).

**Forms of TAC:**
1. **Quadruples:** Each instruction is represented by four fields: operator, argument1, argument2, result.
2. **Triples:** Each instruction is represented by three fields: operator, argument1, argument2. The result is implied.
3. **Indirect Triples:** Like triples but with an additional array of pointers to triples.

**Example:**
For the expression `a + b * c`:
- **Quadruples:**
  ```
  (1)  *   b   c   t1
  (2)  +   a   t1  t2
  ```
- **Triples:**
  ```
  (1)  *   b   c
  (2)  +   a   (1)
  ```
- **Indirect Triples:**
  ```
  (1)  *   b   c
  (2)  +   a   (1)
  Array: [ (1), (2) ]
  ```

### Generating TAC

**Steps:**
1. **Expression Trees:** Convert the source code into an expression tree or AST.
2. **Postorder Traversal:** Traverse the tree in postorder to generate TAC.
3. **Temporary Variables:** Use temporary variables to hold intermediate results.

**Example:**
For the expression `a + b * c`, the steps are:
1. Convert to an expression tree.
2. Postorder traversal: visit `b`, `c`, `*`, `a`, `+`.
3. Generate TAC:
  ```
  t1 = b * c
  t2 = a + t1
  ```

### Advantages of TAC

1. **Simplification:** Simplifies complex expressions into simpler instructions.
2. **Optimization:** Facilitates various optimization techniques like constant folding, dead code elimination, and common subexpression elimination.
3. **Target Code Generation:** Serves as an intermediate step before generating machine code.

# Run-Time Environments

## Stack Allocation of Space

**Definition:**
Stack allocation of space refers to the management of memory for function calls and local variables using a stack data structure. Each function call creates a stack frame (or activation record) that contains all necessary information for the execution of the function.

### Components of a Stack Frame:
1. **Return Address:** The address to return to after the function completes.
2. **Actual Parameters:** The arguments passed to the function.
3. **Saved Machine State:** The values of registers that need to be restored after the function returns.
4. **Local Variables:** The variables declared within the function.
5. **Temporary Storage:** Space for temporary values and intermediate results.

### Process:
1. **Function Call:** When a function is called, a new stack frame is pushed onto the stack.
2. **Function Execution:** The function executes, using the stack frame for its local variables and other data.
3. **Function Return:** When the function completes, its stack frame is popped off the stack, restoring the previous state.

### Example:
Consider the following C function:
```c
void foo(int a, int b) {
    int x = a + b;
    int y = x * 2;
}
```
The stack frame for `foo` would include:
- Return address
- Parameters `a` and `b`
- Local variables `x` and `y`

## Access to Nonlocal Data on the Stack

**Definition:**
Accessing nonlocal data refers to the ability of a function to access variables that are not local to it but are defined in an enclosing scope (e.g., in the case of nested functions).

### Methods:
1. **Static Links:** A pointer in each stack frame that points to the stack frame of the enclosing function. This allows traversing the static chain to access nonlocal variables.
2. **Display:** An array of pointers, where each entry points to the stack frame of an active function at a certain nesting level. This allows direct access to nonlocal variables without traversing the stack.

### Example:
Consider nested functions in a language like Pascal:
```pascal
procedure Outer;
    var x: integer;
    procedure Inner;
    begin
        x := x + 1;  // Accessing nonlocal variable x
    end;
begin
    x := 10;
    Inner;
end;
```
`Inner` can access `x` using either static links or a display to find the stack frame of `Outer`.

## Heap Management

**Definition:**
Heap management involves the allocation and deallocation of memory from the heap, which is a region of memory used for dynamically allocated objects whose lifetimes are not tied to the function call stack.

### Key Concepts:
1. **Dynamic Allocation:** Memory is allocated at runtime using functions like `malloc` in C or `new` in C++.
2. **Deallocation:** Memory must be explicitly freed using functions like `free` in C or `delete` in C++ to avoid memory leaks.
3. **Fragmentation:** Over time, the heap can become fragmented, with free memory divided into small noncontiguous blocks, which can lead to inefficient memory use.

### Garbage Collection:
In languages like Java and Python, garbage collection automatically reclaims memory that is no longer in use, reducing the risk of memory leaks.

### Example:
In C:
```c
int *p = (int*) malloc(sizeof(int) * 10); // Allocate memory for an array of 10 integers
// Use the array
free(p); // Free the allocated memory
```

### Heap Management Techniques:
1. **Free List:** A list of free memory blocks that can be reused for future allocations.
2. **Buddy System:** Memory is allocated in blocks that are powers of two, which simplifies merging and splitting blocks.
3. **Mark and Sweep:** A garbage collection technique that marks reachable objects and then sweeps through memory to collect unmarked objects.
4. **Generational Garbage Collection:** Divides objects into generations and collects younger objects more frequently, based on the observation that most objects die young.

