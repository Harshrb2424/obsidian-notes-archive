
# **Propositional Logic in Artificial Intelligence**

Propositional logic is a fundamental branch of logic used in artificial intelligence to represent and manipulate knowledge in a logical and mathematical form. It deals with propositions that can either be true or false and combines them using logical connectives.

- **Key Concepts**:
    - **Proposition**: A declarative statement that is either true or false.
    - **Logical Connectives**: Operators such as AND, OR, NOT, IMPLIES, and IFF used to combine propositions.
    - **Atomic Propositions**: Simple propositions that consist of a single statement.
    - **Compound Propositions**: Propositions constructed by combining atomic propositions with logical connectives.

- **Examples**:
    - **Atomic Propositions**:
        - "It is Sunday." (True or false)
        - "3 + 3 = 7" (False)
    - **Compound Propositions**:
        - "It is raining today, and the street is wet." (Combines two atomic propositions using "AND")
        - "Ankit is a doctor, and his clinic is in Mumbai." (Combines two atomic propositions using "AND")

- **Logical Connectives**:
    - **AND (∧)**: True if both propositions are true.
    - **OR (∨)**: True if at least one proposition is true.
    - **NOT (¬)**: Inverts the truth value of a proposition.
    - **IMPLIES (→)**: True if the first proposition implies the second.
    - **IFF (↔)**: True if both propositions have the same truth value.

- **Key Terms**:
    - **Tautology**: A proposition that is always true.
    - **Contradiction**: A proposition that is always false.
    - **Contingency**: A proposition that can be either true or false, depending on the situation.

- **Applications in AI**:
    - **Knowledge Representation**: Propositional logic is used to represent and reason about knowledge in AI systems.
    - **Decision Making**: AI agents use propositional logic to evaluate conditions and make decisions based on logical reasoning.
    - **Problem Solving**: Logic-based methods are used in AI for problem-solving tasks such as planning and scheduling.

- **Limitations**:
    - Propositional logic is limited in expressiveness and may not be suitable for representing complex relationships involving variables and quantifiers.
    - Higher-level logics, such as predicate logic, may be more appropriate for complex knowledge representation tasks.


# Set 1
# 1. **Define in your own words: (a) intelligence, (b) artificial intelligence, (c) agent,(d) rationality, (e) logical reasoning** 

- **Intelligence**: Intelligence is the capacity to acquire and apply knowledge and skills, adapt to new situations, solve problems, and make reasoned judgments. It includes the ability to think abstractly, comprehend complex ideas, learn quickly, and learn from experience. It encompasses various cognitive abilities such as memory, perception, reasoning, and verbal and mathematical skills.

- **Artificial Intelligence (AI)**: Artificial Intelligence is the branch of computer science that focuses on creating systems capable of performing tasks that typically require human intelligence. These tasks include learning from experience, adapting to new inputs, understanding natural language, recognizing patterns, and making decisions. AI encompasses a range of approaches and techniques, including machine learning, natural language processing, computer vision, and robotics.

- **Agent**: An agent is an autonomous entity that perceives its environment through sensors, makes decisions based on its perceptions and programmed objectives, and acts upon its environment using actuators. Agents can be simple (e.g., thermostats) or complex (e.g., autonomous vehicles) and may operate in various domains such as robotics, software, or economics.

- **Rationality**: Rationality is the ability to make decisions based on logic, reason, and evidence rather than emotions or subjective preferences. In AI, rationality often refers to the degree to which an agent's actions are aligned with achieving its goals and maximizing its expected utility. Rational agents strive to optimize their outcomes while considering available information and constraints.

- **Logical Reasoning**: Logical reasoning is the process of using formal methods and principles of logic to derive conclusions from given premises or data. It involves the use of systematic steps such as induction, deduction, and abduction to analyze arguments, establish relationships between concepts, and arrive at sound conclusions. Logical reasoning is fundamental to problem-solving and critical thinking in both human and artificial intelligence.
# 2. **Explain with schematic agents and environments.** 

- **Agents**:
    - An agent is an autonomous entity capable of perceiving its environment through sensors and acting upon it through actuators.
    - Agents can be simple (reacting directly to stimuli) or complex (incorporating learning and reasoning capabilities).
    - **Types**:
        - **Simple Reflex Agents**: React to stimuli with pre-defined responses.
        - **Model-Based Reflex Agents**: Maintain an internal model of the environment to make more informed decisions.
        - **Goal-Based Agents**: Act to achieve specific goals.
        - **Utility-Based Agents**: Maximize a utility function to make decisions.
        - **Learning Agents**: Improve their performance over time through learning from experiences.

- **Environments**:
    - The environment is the external context or space in which the agent operates and makes decisions.
    - Environments can vary in complexity, ranging from simple, static scenarios to dynamic, complex ones.
    - **Characteristics**:
        - **Observable vs. Partially Observable**: Fully observable environments provide complete information to the agent, while partially observable environments do not.
        - **Deterministic vs. Stochastic**: In deterministic environments, actions have predictable outcomes, while stochastic environments involve uncertainty.
        - **Discrete vs. Continuous**: Environments can be discrete (with distinct states and actions) or continuous (with a range of possible states and actions).
        - **Static vs. Dynamic**: Static environments remain constant over time, while dynamic environments change independently of the agent's actions.

- **Schematic Representation**:
    - Typically shows the cycle of perception, decision-making, and action between the agent and the environment.
    - Agents receive inputs (perceptions) from the environment and process them to decide on an action.
    - The agent's actions influence the environment, which in turn affects the agent's subsequent perceptions.

- **Agent-Environment Interaction**:
    - **Feedback Loop**: The continuous cycle of perception, decision-making, and action creates a feedback loop between the agent and the environment.
    - **Relational Agents**: Maintain relationships or associations between different aspects of the environment and use this relational knowledge for reasoning and decision-making.
    - **Intelligent Agents**: Utilize advanced reasoning, learning, and decision-making techniques to operate effectively in complex environments.


# 3. **Write an algorithm for a simple problem solving agent** 
A problem-solving agent aims to find a solution to a specific problem using a structured approach. It starts with defining the problem, sets goals, and explores actions until the goal is achieved. This process can be optimized using different search strategies like Hill Climbing and Simulated Annealing algorithms.
### Steps of the Algorithm:
1. **Define the Problem**: 
    - Clearly identify the initial state and goal state.
    - Understand the state space and how each state transitions based on possible actions.

2. **Set Goals**:
    - Establish the desired outcomes or states the agent wants to achieve.

3. **Explore Actions**:
    - Identify the possible actions that can be taken from the current state.
    - Define how actions change the state.

4. **Choose Action**:
    - Use a search strategy (e.g., Hill Climbing, Simulated Annealing) to evaluate possible actions and choose the one that brings the agent closer to its goal.

5. **Update State**:
    - Apply the chosen action and move to a new state.
    - Track the agent's path to the goal state.

6. **Check Goal Achievement**:
    - Evaluate whether the current state meets the goal criteria.
    - If the goal is achieved, terminate the process.

7. **Loop or End**:
    - If the goal is not achieved, loop back to exploring actions and repeat the process.
    - If the goal is achieved, the agent successfully solves the problem and the process ends.

### Search Strategies:

- **Hill Climbing**:
    - A heuristic search algorithm that aims to reach the goal by continuously making the best move from the current state.
    - It evaluates the neighbor states and selects the one with the highest value (best progress towards the goal).
    - Risks include getting stuck in local optima, where the algorithm cannot find a path to the global optimum.

- **Simulated Annealing**:
    - An optimization algorithm inspired by the annealing process in metallurgy.
    - Similar to Hill Climbing, it explores the state space but occasionally accepts worse moves (moves that seem to lead away from the goal) to escape local optima.
    - Uses a temperature parameter that decreases over time, determining the likelihood of accepting worse moves.
    - Useful for complex problems with many local optima.

# 4 **What is Knowledge base agents?**
**Knowledge base agents** in artificial intelligence are systems that use a repository of knowledge to make informed decisions and take actions. These agents can reason, update their knowledge based on observations, and act intelligently based on the information stored in the knowledge base.

- **Knowledge Base**:
    - Contains a collection of facts, rules, and relationships about the world stored in a formal language.
    - Can be structured as propositional logic, first-order logic, or other forms of representation.
    - The knowledge base is dynamic and can be updated based on new observations and information.

- **Inference System**:
    - Utilizes logical rules and algorithms to deduce new information from the knowledge base.
    - Enables the agent to learn and adapt as it reasons through stored knowledge and new observations.
    - Can involve methods such as forward chaining (reasoning from data to conclusions) or backward chaining (reasoning from goals to data).

- **Operations**:
    - **TELL**: Allows the agent to inform the knowledge base of new observations and information.
    - **ASK**: Queries the knowledge base for decision-making, helping the agent choose appropriate actions.
    - **PERFORM**: Executes actions based on the conclusions drawn from the knowledge base.

- **Decision-Making**:
    - Knowledge-based agents use their stored information to make decisions and take actions.
    - Can employ logical reasoning to evaluate multiple possibilities and choose the best course of action.
    - Decisions can be based on deductive, inductive, or abductive reasoning.

- **Learning and Adaptation**:
    - Agents can learn from new data and experiences, updating the knowledge base accordingly.
    - This allows them to adapt to changes in their environment and improve their performance over time.

- **Applications**:
    - Knowledge base agents are used in various fields such as medicine (diagnosis and treatment planning), engineering (design optimization), and finance (risk assessment).
    - They can also be applied in natural language processing, robotics, customer support, and other domains requiring intelligent decision-making.

- **Challenges**:
    - **Knowledge Acquisition**: Gathering and structuring the necessary knowledge can be challenging.
    - **Scalability**: Managing large and complex knowledge bases may require efficient algorithms and data structures.
    - **Uncertainty Handling**: Dealing with incomplete, uncertain, or ambiguous information requires advanced techniques such as probabilistic reasoning.
# 5. **Explain CSP with Examples.**
A Constraint Satisfaction Problem (CSP) is a type of mathematical problem where a solution must satisfy a set of constraints while assigning values to a set of variables. This type of problem is commonly found in areas such as scheduling, planning, and puzzles like Sudoku.

### Components of CSP:
1. **Variables**:
    - These are the parameters or factors that need to be assigned values.
    - For example, in the puzzle "SEND + MORE = MONEY," the variables are the letters S, E, N, D, M, O, R, and Y.

2. **Domain**:
    - The domain is the set of possible values that each variable can take.
    - In the puzzle "SEND + MORE = MONEY," the domain for each letter (variable) is the set of integers from 0 to 9.

3. **Constraints**:
    - Constraints are rules that restrict the values that the variables can take.
    - For example, in "SEND + MORE = MONEY," the constraints include ensuring that:
        - Each letter represents a distinct digit (from 0 to 9).
        - The equation must be satisfied (i.e., the sum of SEND and MORE must equal MONEY).

### Example:
Let's apply CSP to the puzzle "SEND + MORE = MONEY."

1. **Variables**:
    - The variables are the letters S, E, N, D, M, O, R, and Y.
2. **Domain**:
    - The domain for each letter is the set of integers from 0 to 9.
3. **Constraints**:
    - Each letter must represent a distinct digit (from 0 to 9).
    - The sum SEND + MORE must equal MONEY.

#### Example Solution:

In the puzzle "SEND + MORE = MONEY," a valid assignment of values to the letters that satisfies the constraints is:

- `S` = 9
- `E` = 5
- `N` = 6
- `D` = 7
- `M` = 1
- `O` = 0
- `R` = 8
- `Y` = 2

With this assignment, the equation becomes:

- 9567 (SEND)
- +1085 (MORE)
- =10652 (MONEY)

This assignment satisfies the equation and the constraint that each letter represents a distinct digit. Thus, it is a valid solution to the CSP.

# 6. **Write a note on syntax and semantics of First order Logic**

First Order Logic (FOL), also known as predicate logic, is an extension of propositional logic that enables the representation of statements about objects, their properties, and relationships. It allows for more expressive and flexible representations than propositional logic.

#### Syntax of First Order Logic

1. **Symbols**:
    - **Constants**: Represent specific objects or entities in the domain of discourse.
    - **Variables**: Used to refer to objects or entities, can take different values.
    - **Predicates**: Represent relationships among objects or properties of objects.
    - **Functions**: Map objects to other objects.
    - **Logical Connectives**: Operators such as AND (∧), OR (∨), NOT (¬), IMPLIES (→), and IFF (↔).
    - **Quantifiers**: Used to express statements about all or some objects:
        - **Universal Quantifier (∀)**: "For all" or "every" in the domain of discourse.
        - **Existential Quantifier (∃)**: "There exists" or "some" in the domain of discourse.

2. **Formulas**:
    - **Atomic Formulas**: The simplest form of a formula, consisting of a predicate applied to constants or variables (e.g., *Loves(John, Mary)*).
    - **Compound Formulas**: Formed by combining atomic formulas using logical connectives (e.g., *Loves(John, Mary) AND Hates(John, Paul)*).
    - **Quantified Formulas**: Use quantifiers to express statements about a range of objects (e.g., *∀x Loves(John, x)* or *∃y Hates(John, y)*).

#### Semantics of First Order Logic

1. **Interpretation**:
    - An interpretation defines the meaning of symbols in a given domain of discourse.
    - It assigns meanings to constants, variables, predicates, and functions based on the context.

2. **Domain of Discourse**:
    - The domain of discourse is the set of all objects being considered in a particular interpretation.
    
3. **Truth Values**:
    - Statements in FOL are either true or false based on the interpretation.
    - The truth of atomic formulas is determined by the interpretation of predicates applied to objects.
    - The truth of compound formulas is determined using logical connectives.

4. **Satisfaction**:
    - A formula is said to be satisfied in a given interpretation if it evaluates to true.
    - A statement such as *∀x P(x)* is true if P is true for every object in the domain of discourse.
    - A statement such as *∃x P(x)* is true if P is true for at least one object in the domain of discourse.

5. **Models**:
    - A model of a formula is an interpretation in which the formula is true.
    - A formula is valid if it is true in every possible interpretation.
    - A formula is satisfiable if there exists an interpretation in which it is true.

6. **Entailment**:
    - A set of formulas entails another formula if every interpretation that satisfies the set of formulas also satisfies the other formula.


# Set 2
# 1. **What is AI? Give definitions of AI.** 
Artificial Intelligence (AI) is the field of computer science that focuses on creating systems and algorithms capable of performing tasks that typically require human intelligence. These tasks can include learning from data, reasoning, problem-solving, perception, language understanding, and interaction with the environment. AI encompasses a broad range of technologies, from rule-based expert systems to machine learning models and deep neural networks.

- **Simulation of Human Intelligence**: AI involves simulating human cognitive functions in machines, such as visual perception, speech recognition, decision-making, and language translation.

- **Automated Systems**: AI includes the creation of systems that can operate autonomously, making decisions and taking actions to achieve specific goals without human intervention.

- **Rational Agent**: In AI, a rational agent is an entity that perceives its environment and takes actions to achieve the best possible outcome based on its goals and knowledge.

- **Learning and Adaptation**: AI systems often have the ability to learn from data and experiences, adapting their behavior over time to improve performance.

- **General and Narrow AI**: AI can be classified into *narrow AI* (also known as weak AI), which is specialized in performing specific tasks, and *general AI* (also known as strong AI), which has the ability to perform any intellectual task that a human can do.

# 2. **How agent Interacts with environment? Explain with sketch.** 
An agent interacts with its environment through a cycle of perception, decision-making, and action. This cycle can be described as follows:

- **Sensors**: The agent uses sensors to perceive its environment and gather information about the current state of the world. Sensors can be various types of data inputs such as cameras, microphones, or data feeds.

- **Perception**: The agent processes the sensor data to understand its environment. This may involve recognizing patterns, detecting objects, or interpreting events.

- **Decision-Making**: Based on the perception of its environment, the agent makes decisions on the best course of action to achieve its goals. This could involve selecting an action from a set of possible actions.

- **Actuators**: The agent uses actuators to perform actions that influence its environment. Actuators could include motors, robotic arms, or software commands.

- **Feedback Loop**: The actions taken by the agent change the state of the environment, which is then perceived by the agent's sensors. This creates a continuous feedback loop that allows the agent to adapt and adjust its actions as needed.

### Schematic Representation

Here's a conceptual sketch illustrating the agent-environment interaction:
![](https://www.researchgate.net/publication/26589221/figure/fig2/AS:669629118685198@1536663431720/Agents-interact-with-environments-through-sensors-and-effectors-A-rational-agent-is-one.ppm)

- **Percepts**: This is the input from the environment to the agent, often in the form of sensor data.

- **Actions**: This is the output from the agent to the environment, usually implemented through actuators.

# 3. **A simple problem solving agent, explain with functional code.** 
A simple problem-solving agent operates by following a structured approach to define and solve problems. Here are the key steps involved, along with a brief overview of functional code:

- **Problem Definition**: Define the problem by specifying the initial state and goal state. This sets the boundaries for the agent's search for a solution.

- **Search Algorithm**: Implement a search algorithm (e.g., breadth-first search, depth-first search) to explore possible actions and find a path from the initial state to the goal state.

- **State Transition**: Given an action, the agent transitions from the current state to a new state. The `execute` function represents this transition.

- **Goal Test**: The agent tests whether the current state matches the goal state. If the goal state is reached, the agent stops searching.

- **Solve Function**: The main function that drives the agent's problem-solving process. It iteratively searches for actions and executes them until the goal is reached.

```c
# Example usage
initial_state = 0
goal_state = 10
problem = Problem(initial_state, goal_state)
agent = ProblemSolvingAgent(problem)

solution = agent.solve()
```

- **Functional Code**: 
    - Define a `Problem` class with `initial_state`, `goal_state`, and a `goal_test` method.
    - Define a `ProblemSolvingAgent` class with a `search` method to determine the next action and an `execute` method to transition to a new state.
    - The agent uses these methods in a loop to solve the problem.

# 4. **What is multi-agent environments in adversarial search?**
A multi-agent environment in adversarial search is a scenario in artificial intelligence where multiple agents are competing against each other to achieve their respective goals. These agents operate in a shared environment, and each agent's success often comes at the expense of others. 

- **Adversarial Setting**: Agents in the environment are competitors, aiming to maximize their own utility while minimizing the utility of their opponents.

- **Game Theory**: Multi-agent adversarial environments often involve game theory concepts, where agents strategize based on the actions and possible responses of others.

- **Minimax and Alpha-Beta Pruning**: Common techniques used by agents in adversarial search to decide optimal moves and efficiently navigate the search space.

- **Strategic Decision-Making**: Agents must consider the actions of other agents when making decisions, choosing actions that improve their own position while hindering their opponents.

- **Examples**: Classic examples include strategic games such as chess and Go, where two players compete against each other.

Multi-agent environments in adversarial search involve multiple agents competing strategically in an environment, using various techniques to optimize their own objectives while countering their opponents' moves.

# 5. **Write a note on Optimal decisions in games, with examples**
Optimal decision-making in games involves choosing the best possible moves to maximize one's advantage while minimizing potential losses.

- **Game Types**:
    - **Zero-sum games**: One player's gain is another player's loss (e.g., chess).
    - **Non-zero-sum games**: Players can cooperate or compete for mutual benefit (e.g., Settlers of Catan).

- **Strategies**:
    - **Dominant strategy**: Best strategy regardless of the opponent's actions.
    - **Nash equilibrium**: No player can improve their outcome by unilaterally changing strategy.
    - **Mixed strategies**: Randomizing moves to keep opponents uncertain.

- **Min-Max Method**:
    - Focuses on minimizing the maximum possible loss.
    - Common in zero-sum games like tic-tac-toe or chess.

- **Expectiminimax Algorithm**:
    - Used in games with probabilistic elements (e.g., card games).
    - Considers possible outcomes and their probabilities to maximize expected utility.

- **Monte Carlo Tree Search (MCTS)**:
    - Simulates random games and evaluates potential outcomes.
    - Useful in complex games like Go and real-time strategy games.

#### Examples of Optimal Decisions:

- **Chess**:
    - Evaluate possible moves and counter-moves.
    - Choose moves that maximize potential gains and control the board.

- **Poker**:
    - Weigh potential gains against risks based on probabilities.
    - Decide whether to bet, call, raise, or fold based on expected outcomes.

- **Settlers of Catan**:
    - Balance resource acquisition with limiting opponents' access.
    - Choose placements and trades that maximize your resource flow.

- **Sudoku**:
    - Fill the grid with numbers while adhering to the rules.
    - Choose moves that maximize filled cells without breaking the rules.
### Min-Max in Single-Player Games:

- In single-player games, the player aims to maximize their own score or progress while minimizing potential losses or risks.

1. **Optimal Strategy**:
    - The player chooses the move that results in the highest minimum value from a set of choices.
  
2. **Example**: 
    - Given a set of possible outcomes (3, 12, 8), (2, 4, 6), (14, 5, 12), the player must choose one of the tuples.
    - Calculate the minimum value in each tuple: `min(3, 12, 8) = 3`, `min(2, 4, 6) = 2`, `min(14, 5, 12) = 5`.
    - Next, select the maximum value from these minimums: `max(3, 2, 5) = 5`.
    - Thus, the optimal decision is to choose the tuple `(14, 5, 12)` as it results in the maximum of the minimum values.

### Min-Max in Multi-Player Games:

- In multi-player games, each player aims to maximize their own score while considering the other players' strategies.

1. **Optimal Strategy**:
    - Each player chooses the move that maximizes their minimum payoff given the possible moves of other players.
    - In a multi-player scenario, the Min-Max method can be applied to each player's perspective.

2. **Example**:
    - Given a set of tuples representing payoffs for players A, B, and C: 
        - `(1, 2, 7)`, `(5, 13, 16)`, `(6, 8, 1)`, `(4, 7, 14)`, `(12, 6, 16)`, `(2, 6, 1)`.
    - Calculate the max payoff for each tuple for each player:
        - Player A's maximums: `max(1, 5, 6, 4, 12, 2) = 12`.
        - Player B's maximums: `max(2, 13, 8, 7, 6, 6) = 13`.
        - Player C's maximums: `max(7, 16, 1, 14, 16, 1) = 16`.
    - Therefore, the optimal decision for each player based on the Min-Max method would be as follows:
        - Player A's optimal choice is the tuple `(12, 6, 16)`, as it gives them the maximum possible value of 12.
        - Player B's optimal choice is the tuple `(5, 13, 16)`, as it gives them the maximum possible value of 13.
        - Player C's optimal choice is the tuple `(5, 13, 16)`, as it gives them the maximum possible value of 16.

# 6. **Explain first order Logic**
First Order Logic (FOL), also known as predicate logic, is a formal system for representing and reasoning about statements that involve objects, their properties, and relationships among them. FOL extends propositional logic by introducing quantifiers, predicates, and functions, enabling more expressive and flexible statements about the world.

1. **Domain of Discourse**:
    - The domain of discourse is the set of all objects being considered in a particular scenario.
    - It defines the set of entities over which quantifiers range.

2. **Symbols**:
    - **Constants**: Symbols that represent specific objects in the domain (e.g., `John`, `Mary`).
    - **Variables**: Symbols that can take any value from the domain (e.g., `x`, `y`).
    - **Predicates**: Symbols that represent properties of objects or relationships between them (e.g., `Loves`, `Teaches`).
    - **Functions**: Symbols that map objects to other objects (e.g., `MotherOf`, `SquareOf`).
    - **Logical Connectives**: Operators such as AND (∧), OR (∨), NOT (¬), IMPLIES (→), and IFF (↔).
    - **Quantifiers**: Symbols that express the extent to which a predicate holds over a range of objects:
        - **Universal Quantifier (∀)**: Expresses that a statement is true for all objects in the domain (`For all x, P(x)`).
        - **Existential Quantifier (∃)**: Expresses that a statement is true for at least one object in the domain (`There exists x such that P(x)`).

3. **Formulas**:
    - **Atomic Formulas**: Simple statements involving predicates applied to constants or variables (e.g., `Loves(John, Mary)`).
    - **Compound Formulas**: Formed by combining atomic formulas using logical connectives (e.g., `Loves(John, Mary) ∧ Hates(John, Paul)`).
    - **Quantified Formulas**: Statements that include quantifiers (e.g., `∀x Loves(John, x)` or `∃y Hates(John, y)`).

4. **Syntax**:
    - The syntax of FOL defines how statements can be constructed using the symbols and logical connectives.

5. **Semantics**:
    - **Interpretation**: Defines the meaning of symbols in a given domain of discourse, including what each constant, predicate, and function represents.
    - **Truth Values**: Determines whether a statement is true or false based on its interpretation.
    - **Satisfaction**: A statement is satisfied in an interpretation if it evaluates to true.
    - **Models**: An interpretation in which a formula is true is called a model of the formula.
    - **Entailment**: A set of formulas entails another formula if every interpretation that satisfies the set of formulas also satisfies the other formula.

6. **Resolution**:
    - A proof technique used in FOL that builds refutation proofs (proofs by contradiction).
    - Clauses are disjunctions of literals, and FOL statements must be converted into Conjunctive Normal Form (CNF) for resolution.

### Examples of First Order Logic
- **Predicate and Quantifiers**:
    - `Loves(John, Mary)`: An atomic formula stating that John loves Mary.
    - `∀x Loves(John, x)`: A quantified formula stating that John loves everyone in the domain.
    - `∃y Hates(John, y)`: A quantified formula stating that there is at least one person John hates.

- **Combining Logical Connectives**:
    - `Loves(John, Mary) ∧ Hates(Paul, John)`: A compound formula stating that John loves Mary and Paul hates John.
    - `∀x (Loves(John, x) → Teaches(John, x))`: A quantified formula stating that if John loves someone, he teaches them.