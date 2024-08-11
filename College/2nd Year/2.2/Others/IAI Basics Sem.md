# Unit 1
### **1. Intelligent Agents**

**Definition:** 
An intelligent agent is an entity that perceives its environment through sensors and acts upon that environment through actuators. It can be a software program, a robot, or even a human.

**Key Components:**
- **Sensors:** Collect data from the environment.
- **Actuators:** Perform actions based on the agent's decisions.
- **Agent Program:** The algorithm or set of rules that determines the agent's behavior.

**Types of Agents:**
- **Simple Reflex Agents:** Act based on the current percept, ignoring the history of past perceptions.
- **Model-Based Reflex Agents:** Maintain an internal model of the world to account for partial observability.
- **Goal-Based Agents:** Act to achieve specific goals and consider future actions.
- **Utility-Based Agents:** Choose actions that maximize a utility function, considering both goals and preferences.
- **Learning Agents:** Improve their performance over time based on experience.

### **2. Problem-Solving Agents**

**Definition:**
A problem-solving agent is designed to solve problems by finding a sequence of actions that lead to a desired goal. It uses search algorithms to explore possible solutions.

**Key Concepts:**
- **State Space:** The set of all possible states in a problem.
- **Actions:** Operations that transition from one state to another.
- **Goal State:** The state that the agent aims to achieve.
- **Path Cost:** The total cost of reaching the goal state from the initial state.

### **3. Searching for Solutions**

**Search algorithms are techniques used to find a solution to a problem by exploring the state space. Here are some common search algorithms:**

**a. Breadth-First Search (BFS):**

- **Approach:** Explores all nodes at the present depth level before moving on to nodes at the next depth level.
- **Properties:**
  - Complete: Guarantees finding a solution if one exists.
  - Optimal: Finds the shortest path if all actions have equal cost.
  - Space Complexity: Can be high as it stores all nodes at a given depth level.
- **Use Case:** Suitable for problems where the shortest path is desired, and the state space is not too large.

**b. Depth-First Search (DFS):**

- **Approach:** Explores as far as possible along one branch before backtracking.
- **Properties:**
  - Not complete: May get stuck in infinite loops.
  - Not optimal: May not find the shortest path.
  - Space Complexity: Generally lower than BFS as it only stores nodes along the current path.
- **Use Case:** Useful for problems with large state spaces or when exploring deep solutions is preferable.

**c. Hill-Climbing Search:**

- **Approach:** Continuously moves towards the direction of increasing value or utility to reach the goal.
- **Properties:**
  - Greedy: Only considers immediate gains and may not find the global optimum.
  - Can get stuck in local maxima or plateaus.
- **Use Case:** Effective when the goal is to find a good enough solution quickly and the state space has a clear gradient.

**d. Simulated Annealing Search:**

- **Approach:** Uses random sampling and probabilistic techniques to escape local maxima by allowing worse moves with decreasing probability over time.
- **Properties:**
  - Complete: Can find the global optimum given enough time and appropriate cooling schedule.
  - Involves cooling schedule: Determines how the probability of accepting worse solutions decreases over time.
- **Use Case:** Suitable for optimization problems where the state space is large and complex.

**e. Local Search in Continuous Spaces:**

- **Approach:** Works in continuous spaces where the goal is to find a local optimum by iteratively improving solutions.
- **Techniques:**
  - **Gradient Descent:** Moves in the direction of the negative gradient to minimize a cost function.
  - **Genetic Algorithms:** Uses evolutionary principles to explore and exploit the search space.
- **Properties:**
  - Useful for problems where the solution space is continuous and high-dimensional.
  - Can be prone to local optima but can be combined with techniques like simulated annealing to improve results.
# Unit 2
### **1. Games**

**a. Optimal Decisions in Games**

- **Definition:** Optimal decisions in games involve selecting strategies that maximize an agent's chances of winning or achieving the best possible outcome.
- **Minimax Algorithm:** A common method for optimal decision-making in two-player, zero-sum games. The algorithm assumes that the opponent is also playing optimally.
  - **Minimizing Player:** Tries to minimize the maximum possible loss.
  - **Maximizing Player:** Tries to maximize the minimum possible gain.
- **Game Tree:** A representation of all possible moves in a game, where nodes represent game states and edges represent moves.

**b. Alpha–Beta Pruning**

- **Definition:** An optimization technique for the minimax algorithm to reduce the number of nodes evaluated in the game tree.
- **Approach:**
  - **Alpha Value:** The best value that the maximizing player can guarantee so far.
  - **Beta Value:** The best value that the minimizing player can guarantee so far.
  - **Pruning:** If the current node's value is worse than the alpha or beta value, further exploration of that node is skipped.
- **Benefits:** Reduces the computational cost by eliminating branches that do not affect the final decision.

### **2. Constraint Satisfaction Problems (CSPs)**

**a. Defining Constraint Satisfaction Problems**

- **Definition:** CSPs involve finding values for variables that satisfy a set of constraints.
- **Components:**
  - **Variables:** Elements that need to be assigned values.
  - **Domains:** Possible values for each variable.
  - **Constraints:** Rules that restrict the values variables can take.

**b. Constraint Propagation**

- **Definition:** A technique to reduce the search space by applying constraints to eliminate impossible values from variable domains.
- **Methods:**
  - **Forward Checking:** Checks constraints as soon as a variable is assigned a value, reducing domains of unassigned variables.
  - **Arc Consistency:** Ensures that for every value of one variable, there is a consistent value for another variable.

**c. Backtracking Search for CSPs**

- **Definition:** A systematic method for exploring possible assignments of values to variables while checking constraints.
- **Approach:**
  - **Assignment:** Assign values to variables incrementally.
  - **Checking:** Verify that each assignment satisfies the constraints.
  - **Backtrack:** If a constraint is violated, undo the last assignment and try a different value.

### **3. Knowledge-Based Agents**

- **Definition:** Agents that use knowledge and reasoning to make decisions based on the current state and their knowledge base.
- **Components:**
  - **Knowledge Base:** A collection of facts and rules about the domain.
  - **Inference Engine:** A mechanism for deriving new knowledge from the knowledge base.

### **4. Logic**

**a. Propositional Logic**

- **Definition:** A branch of logic dealing with propositions that can be either true or false.
- **Propositions:** Simple statements or variables that can have truth values.
- **Logical Connectives:** AND, OR, NOT, IMPLIES, and BICONDITIONAL used to form compound propositions.

**b. Propositional Theorem Proving**

- **Inference and Proofs:**
  - **Inference:** Deriving new propositions from existing ones using logical rules.
  - **Proofs:** A sequence of logical steps that demonstrates the truth of a proposition.

- **Proof by Resolution:**
  - **Definition:** A method of proof that uses the principle of resolution to derive a contradiction, proving that the original proposition is true.
  - **Approach:** Convert propositions to Conjunctive Normal Form (CNF) and apply resolution rules to derive new clauses until an empty clause is obtained.

- **Horn Clauses and Definite Clauses:**
  - **Horn Clauses:** A type of clause in propositional logic with at most one positive literal.
  - **Definite Clauses:** Horn clauses with exactly one positive literal. Useful in logic programming and rule-based systems.
  - **Properties:** Horn clauses are particularly useful because they allow for efficient algorithms for theorem proving.

# Unit 3
### **1. First-Order Logic (FOL)**

**a. Syntax and Semantics of First-Order Logic**

- **Syntax:**
  - **Constants:** Represent specific objects (e.g., `John`, `Mary`).
  - **Variables:** Represent objects that can be anything (e.g., `x`, `y`).
  - **Predicates:** Functions that return true or false (e.g., `Loves(John, Mary)`).
  - **Functions:** Map objects to objects (e.g., `MotherOf(John)`).
  - **Logical Connectives:** AND, OR, NOT, IMPLIES, and BICONDITIONAL.
  - **Quantifiers:** 
    - **Universal Quantifier (∀):** Represents "for all" (e.g., `∀x Loves(x, Mary)`).
    - **Existential Quantifier (∃):** Represents "there exists" (e.g., `∃x Loves(x, Mary)`).

- **Semantics:**
  - **Interpretation:** Assigns meanings to constants, predicates, and functions in a specific domain of discourse.
  - **Model:** An interpretation that makes all sentences in a knowledge base true.

**b. Using First-Order Logic**

- **Knowledge Representation:** FOL is used to represent complex relationships and facts in a structured way. 
- **Expressiveness:** Allows for more detailed and specific representations compared to propositional logic.

**c. Knowledge Engineering in First-Order Logic**

- **Definition:** The process of designing and developing knowledge-based systems using FOL.
- **Tasks:**
  - **Domain Modeling:** Identifying and defining the relevant objects, relationships, and constraints in a domain.
  - **Rule Creation:** Formulating rules and facts that represent the domain knowledge in FOL.

### **2. Inference in First-Order Logic**

**a. Propositional vs. First-Order Inference**

- **Propositional Inference:**
  - Deals with propositions that are either true or false.
  - Uses logical connectives and inference rules like modus ponens and resolution.

- **First-Order Inference:**
  - Involves variables and quantifiers.
  - Requires additional techniques like unification and quantifier manipulation.

**b. Unification**

- **Definition:** A process of finding a substitution for variables that makes different logical expressions identical.
- **Purpose:** Used in automated theorem proving and logic programming.
- **Example:** To unify `Loves(x, Mary)` and `Loves(John, y)`, the substitution `{x/John, y/Mary}` makes both expressions identical.

**c. Forward Chaining**

- **Definition:** An inference method that starts with known facts and applies rules to infer new facts.
- **Approach:** Uses a data-driven approach to add new facts to the knowledge base until the goal is reached.
- **Use Case:** Effective in rule-based systems and production systems.

**d. Backward Chaining**

- **Definition:** An inference method that starts with a goal and works backward to determine the necessary conditions to achieve it.
- **Approach:** Uses a goal-driven approach to find which facts and rules are required to satisfy the goal.
- **Use Case:** Commonly used in logic programming and expert systems.

**e. Resolution**

- **Definition:** A proof technique that derives contradictions from a set of clauses to prove that a proposition is true.
- **Approach:**
  - Convert sentences to Conjunctive Normal Form (CNF).
  - Apply the resolution rule to pairs of clauses to derive new clauses.
  - Continue until an empty clause (contradiction) is derived or no new clauses can be derived.
- **Use Case:** Widely used in automated theorem proving and logic-based reasoning systems.
# 3.2
### **1. Ontological Engineering**

**Definition:**
Ontological engineering involves creating and managing ontologies, which are formal representations of knowledge within a domain. It defines the types of entities and their relationships in a structured way to facilitate understanding, communication, and reasoning.

**Components:**
- **Ontology:** A formal, explicit specification of a shared conceptualization. It includes concepts (classes), relationships (properties), and instances (individuals).
- **Concepts (Classes):** Categories or types of objects within the domain (e.g., `Person`, `Vehicle`).
- **Relationships (Properties):** Connections between concepts (e.g., `owns`, `drives`).
- **Instances (Individuals):** Specific objects or entities in the domain (e.g., `John`, `Toyota`).

**Process:**
1. **Ontology Development:** Identifying and defining key concepts, relationships, and constraints within a domain.
2. **Ontology Implementation:** Encoding the ontology in a formal language like OWL (Web Ontology Language) or RDF (Resource Description Framework).
3. **Ontology Evaluation:** Ensuring the ontology accurately represents the domain and is usable for its intended purposes.

**Tools:**
- **Protégé:** A popular tool for creating and managing ontologies.
- **OWL:** A web ontology language used for defining and instantiating ontologies.

### **2. Categories and Objects**

**Categories (Classes):**
- **Definition:** Abstract groups or types that share common properties or characteristics.
- **Purpose:** Help in organizing and classifying objects within a domain.
- **Examples:** `Animal`, `Book`, `Employee`.

**Objects (Instances):**
- **Definition:** Specific entities or individuals that belong to categories.
- **Purpose:** Represent concrete examples of the abstract categories.
- **Examples:** `Tiger` (an instance of `Animal`), `Moby Dick` (an instance of `Book`).

**Hierarchy:**
- **Subclass:** A category that inherits properties from a parent category (e.g., `Dog` is a subclass of `Animal`).
- **Superclass:** A category that is a parent to one or more subclasses (e.g., `Animal` is a superclass of `Dog`).

### **3. Events**

**Definition:**
Events represent occurrences or actions that happen within a domain. They can affect the state of objects or entities and are often used to describe changes or interactions.

**Components:**
- **Event Types:** General categories of events (e.g., `Transaction`, `Meeting`).
- **Event Instances:** Specific occurrences of events (e.g., `Purchase of laptop`, `Team meeting on Monday`).

**Characteristics:**
- **Temporal Aspects:** Events have a time component, indicating when they occur (e.g., `2024-07-30`).
- **Participants:** Entities involved in the event (e.g., `John` and `Mary` in a `Meeting` event).
- **Effects:** Changes or outcomes resulting from the event (e.g., `Item added to cart`, `Task completed`).

**Representation:**
- **Event Ontologies:** Ontologies specifically designed to model events and their relationships (e.g., Event Ontology, Dublin Core Metadata Initiative).
- **Temporal Logic:** Used to represent and reason about temporal aspects of events.

# Unit 4
### **1. Definition of Classical Planning**

**Classical Planning:**
- **Definition:** A type of planning that involves generating a sequence of actions to transition from an initial state to a goal state in a deterministic environment.
- **Assumptions:**
  - The environment is fully observable.
  - The effects of actions are predictable and deterministic.
  - Actions are discrete and have well-defined preconditions and effects.

**Components:**
- **Initial State:** The starting condition of the environment.
- **Goal State:** The desired condition to be achieved.
- **Actions:** Operations that can be performed to change the state of the environment.
- **Plan:** A sequence of actions that transforms the initial state into the goal state.

### **2. Algorithms for Planning with State Space Search**

**State Space Search:**
- **Definition:** A method of finding a sequence of actions by exploring the state space, which represents all possible states and transitions between them.

**Algorithms:**

- **Breadth-First Search (BFS):**
  - **Approach:** Explores all possible actions at the current depth level before moving to the next level.
  - **Properties:** Guarantees finding the shortest path if the path cost is uniform.

- **Depth-First Search (DFS):**
  - **Approach:** Explores as far as possible along one branch before backtracking.
  - **Properties:** May not find the shortest path and can get stuck in infinite loops.

- **A* Search:**
  - **Approach:** Uses a heuristic function to estimate the cost from the current state to the goal, combining path cost and heuristic cost.
  - **Properties:** Finds the optimal path if the heuristic is admissible (never overestimates the cost).

- **Iterative Deepening Search (IDS):**
  - **Approach:** Combines the depth-first search’s space efficiency with the breadth-first search’s completeness by progressively increasing the depth limit.
  - **Properties:** Useful when the depth of the solution is unknown.

### **3. Planning Graphs**

**Definition:**
- **Planning Graph:** A data structure used to represent the state space in planning problems, capturing both actions and their effects over a series of time steps.

**Components:**
- **Levels:** Alternating layers of proposition levels (states) and action levels.
- **Propositions:** Conditions that are true or false at a given level.
- **Actions:** Operations that can change the propositions from one level to the next.

**Purpose:**
- **Graph Plan Algorithm:** Uses planning graphs to find a valid sequence of actions by ensuring that actions achieve the desired propositions and that no actions interfere with each other.

### **4. Other Classical Planning Approaches**

**STRIPS (Stanford Research Institute Problem Solver):**
- **Definition:** A formalism for classical planning problems involving actions with preconditions and effects.
- **Approach:** Uses operators with specified conditions for their execution and effects on the state.

**GraphPlan:**
- **Definition:** An algorithm that constructs a planning graph to derive a plan by analyzing the graph’s structure.
- **Approach:** Builds a planning graph incrementally and checks for plan feasibility based on goal satisfaction and action constraints.

**HTN (Hierarchical Task Network) Planning:**
- **Definition:** A planning approach that decomposes high-level tasks into simpler subtasks in a hierarchical manner.
- **Approach:** Focuses on breaking down complex tasks into manageable components and solving them at various levels of abstraction.

### **5. Analysis of Planning Approaches**

**Criteria for Analysis:**
- **Completeness:** Whether the algorithm guarantees finding a solution if one exists.
- **Optimality:** Whether the algorithm finds the best solution in terms of cost or length.
- **Efficiency:** How well the algorithm performs with respect to computational resources (time and space).
- **Scalability:** How well the algorithm handles increasing problem sizes and complexities.

**Comparison:**
- **State Space Search Algorithms:** Effective for simpler problems but may struggle with large or complex state spaces.
- **Planning Graphs:** Useful for handling complex interactions and constraints but may require significant computational resources.
- **HTN Planning:** Provides a more structured approach by breaking down tasks but may be less flexible compared to other methods.

### **6. Hierarchical Planning**

**Definition:**
- **Hierarchical Planning:** An approach that decomposes high-level goals into a hierarchy of subgoals and tasks.
- **Components:**
  - **High-Level Goals:** Broad objectives that need to be achieved.
  - **Subgoals and Tasks:** Specific actions or intermediate goals needed to achieve the high-level goals.
  - **Task Decomposition:** Breaking down tasks into simpler, more manageable subtasks.

**Benefits:**
- **Modularity:** Allows for planning at different levels of abstraction, making complex problems more manageable.
- **Reusability:** Subtasks can be reused across different plans, improving efficiency and consistency.

**Approaches:**
- **Hierarchical Task Network (HTN) Planning:** A specific method for hierarchical planning that uses a hierarchical structure to organize tasks and goals.

# Unit 5
### **1. Acting under Uncertainty**

**Definition:**
- **Acting under Uncertainty:** Involves making decisions or predictions in situations where there is incomplete or ambiguous information about the environment or outcomes.

**Approaches:**
- **Probabilistic Models:** Use probability theory to represent and reason about uncertainty.
- **Decision Theory:** Incorporates probabilities to make rational decisions considering the risks and benefits.
- **Bayesian Inference:** Updates probabilities as new information becomes available.

### **2. Basic Probability Notation**

**Key Concepts:**
- **Probability (P):** A measure of the likelihood of an event occurring, ranging from 0 (impossible) to 1 (certain).
  - **P(A):** Probability of event A.
- **Conditional Probability (P(A|B)):** The probability of event A given that event B has occurred.
- **Joint Probability (P(A, B)):** The probability of both events A and B occurring together.
- **Marginal Probability (P(A)):** The probability of event A without considering other events.
- **Complementary Probability (P(A’)):** The probability of event A not occurring.

**Formulas:**
- **Addition Rule:** P(A ∪ B) = P(A) + P(B) - P(A ∩ B)
- **Multiplication Rule:** P(A ∩ B) = P(A) * P(B|A) = P(B) * P(A|B)

### **3. Bayes’ Rule and Its Use**

**Definition:**
- **Bayes’ Rule:** A fundamental theorem in probability theory that describes how to update the probability of a hypothesis based on new evidence.

**Formula:**
$P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}$

**Components:**
- **P(A|B):** Posterior probability (probability of A given B).
- **P(B|A):** Likelihood (probability of B given A).
- **P(A):** Prior probability (initial probability of A).
- **P(B):** Marginal likelihood (total probability of B).

**Use Cases:**
- **Diagnostic Applications:** Updating probabilities of diseases based on test results.
- **Spam Filtering:** Classifying emails as spam or non-spam based on features.

### **4. Probabilistic Reasoning**

**Definition:**
- **Probabilistic Reasoning:** The process of making inferences and decisions based on probabilistic models and principles.

**Techniques:**
- **Bayesian Networks:** Graphical models that represent probabilistic relationships among variables.
- **Markov Chains:** Models that describe systems with probabilistic state transitions.
- **Monte Carlo Methods:** Statistical techniques used for approximating solutions through random sampling.

### **5. Representing Knowledge in an Uncertain Domain**

**Approaches:**
- **Probability Distributions:** Represent the likelihood of various outcomes or states.
- **Bayesian Networks:** Represent dependencies among variables using nodes and edges.
- **Fuzzy Logic:** Uses degrees of membership to represent uncertainty in a non-binary manner.

**Examples:**
- **Medical Diagnosis:** Representing the probability of diseases based on symptoms and test results.
- **Weather Forecasting:** Modeling the probability of different weather conditions based on historical data.

### **6. The Semantics of Bayesian Networks**

**Definition:**
- **Bayesian Networks:** Directed acyclic graphs (DAGs) where nodes represent random variables and edges represent conditional dependencies.

**Components:**
- **Nodes:** Represent variables (e.g., disease, symptoms).
- **Edges:** Represent conditional dependencies (e.g., symptoms depend on disease).
- **Conditional Probability Tables (CPTs):** Specify the probability of each node given its parents.

**Semantics:**
- **Joint Probability Distribution:** The network represents a joint probability distribution over all variables.
- **Factorization:** The joint probability is factored into a product of conditional probabilities.

### **7. Efficient Representation of Conditional Distributions**

**Techniques:**
- **Factor Graphs:** Represent complex conditional distributions as a product of simpler factors.
- **Sparse Representations:** Store only non-zero probabilities to save space and computation.

**Examples:**
- **Belief Networks:** Represent dependencies among variables in a compact form.
- **Markov Random Fields:** Capture pairwise dependencies in undirected graphs.

### **8. Approximate Inference in Bayesian Networks**

**Definition:**
- **Approximate Inference:** Techniques used when exact inference is computationally infeasible.

**Methods:**
- **Monte Carlo Sampling:** Uses random samples to estimate probabilities.
- **Variational Methods:** Approximate the true distribution by optimizing a simpler distribution.
- **Loopy Belief Propagation:** Iterative method for approximate inference in networks with cycles.

**Use Cases:**
- **Large-Scale Networks:** Handling complex networks with many variables and dependencies.
- **Real-Time Systems:** Providing quick estimates in dynamic environments.

### **9. Relational and First-Order Probability**

**Relational Probability:**
- **Definition:** Extends probabilistic reasoning to relational data, where relationships among objects are considered.
- **Examples:** Probabilistic logic programming and relational Bayesian networks.

**First-Order Probability:**
- **Definition:** Applies probability theory to first-order logic, where predicates and variables represent relationships and objects.
- **Applications:** Modeling uncertainty in complex domains with variable relationships.

**Techniques:**
- **Probabilistic Logic Programming:** Combines logic programming with probabilistic reasoning.
- **Markov Logic Networks:** Integrates first-order logic with probabilistic graphical models.

