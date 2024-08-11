### Acting under Uncertainty

**Definition**: Acting under Uncertainty refers to making decisions in situations where outcomes are not completely predictable due to incomplete information or stochastic elements.

**Key Concepts**:

- **Uncertain Environments**: Includes situations where the consequences of actions are not fully known or are probabilistic.
  
- **Decision Making**: Involves strategies such as risk assessment, expected utility, and decision trees to optimize outcomes despite uncertainty.

**Approaches**:

- **Probabilistic Models**: Represent uncertainty using probabilities, enabling reasoning about likely outcomes and optimal decisions.

- **Decision Theory**: Provides frameworks like Expected Utility Theory to quantify preferences and make rational decisions under uncertainty.

### Basic Probability Notation

**Probability Basics**:

- **Sample Space**: Set of all possible outcomes of an experiment.
  
- **Event**: Subset of the sample space, representing a set of outcomes.
  
- **Probability**: Measure of the likelihood of an event occurring, typically denoted as P(event).

**Operations**:

- **Union and Intersection**: P(A ∪ B) denotes the probability of either A or B occurring; P(A ∩ B) denotes the probability of both A and B occurring.
  
- **Complement**: P(A') denotes the probability of the complement of event A (not A).

**Conditional Probability**:

- **Definition**: P(A | B) denotes the probability of event A occurring given that event B has occurred.
  
- **Formula**: P(A | B) = P(A ∩ B) / P(B), where P(B) ≠ 0.

### Bayes' Rule and Its Use

**Bayes' Rule**:

- **Formula**: P(A | B) = P(B | A) * P(A) / P(B), where:
  - P(A | B) is the probability of A given B.
  - P(B | A) is the probability of B given A.
  - P(A) and P(B) are the probabilities of A and B respectively.

**Applications**:

- **Bayesian Inference**: Updates prior beliefs (P(A)) based on new evidence (P(B | A)) to calculate posterior probabilities (P(A | B)).
  
- **Diagnostic Reasoning**: Calculates probabilities of diseases given symptoms, incorporating prior knowledge and observed data.

**Use Cases**:

- **Machine Learning**: Bayesian networks use Bayes' Rule for probabilistic graphical models, aiding in decision-making under uncertainty.
  
- **Medical Diagnosis**: Determines disease probabilities based on symptoms and patient history.
### Probabilistic Reasoning

**Definition**: Probabilistic Reasoning involves making decisions and predictions under uncertainty using probability theory.

**Key Concepts**:

- **Uncertainty Types**: Includes stochastic outcomes, incomplete information, and ambiguity in decision-making.
  
- **Probabilistic Models**: Represent uncertainty using probabilities, enabling quantitative reasoning about likely outcomes.

**Approaches**:

- **Bayesian Networks**: Graphical models that encode probabilistic relationships between variables.
  
- **Decision Theory**: Frameworks like Expected Utility Theory to optimize decisions given uncertain outcomes.

**Applications**:

- **AI Planning**: Incorporates uncertainty into plans and strategies.
  
- **Medical Diagnosis**: Calculates probabilities of diseases based on symptoms and patient history.

### Representing Knowledge in an Uncertain Domain

**Challenges**:

- **Incomplete Information**: Missing or uncertain data affecting decision-making.
  
- **Stochastic Processes**: Random variables influencing outcomes.

**Techniques**:

- **Probability Distributions**: Model uncertainty using distributions like Gaussian, Bernoulli, or Poisson.
  
- **Belief Networks**: Represent conditional dependencies between variables using directed acyclic graphs (DAGs).

**Example**:

- **Weather Prediction**: Using historical data and probabilistic models to forecast future weather conditions.

### The Semantics of Bayesian Networks

**Bayesian Networks (BN)**:

- **Definition**: Graphical representation of probabilistic relationships between variables, based on Bayes' Rule.
  
- **Components**:
  - **Nodes**: Represent variables, each with a probability distribution.
  - **Edges**: Directed edges denote probabilistic dependencies between variables.
  - **Conditional Probabilities**: Quantify how one variable influences another.

**Semantics**:

- **Conditional Independence**: Nodes are conditionally independent of their non-descendants given their parents.
  
- **Propagation**: Update beliefs (probabilities) using evidence and probabilistic inference algorithms (like Pearl's Belief Propagation).

**Use Cases**:

- **Medical Diagnosis**: Bayesian networks aid in diagnosing diseases based on symptoms and test results.
  
- **Risk Assessment**: Evaluate probabilities of risks and mitigating factors in decision-making scenarios.

### Efficient Representation of Conditional Distributions

**Challenges**:

- **Complexity**: Large state spaces and dependencies increase computational complexity.
  
- **Storage**: Efficiently storing and accessing conditional probabilities.

**Techniques**:

- **Parameterization**: Represent distributions using parameters (e.g., mean and variance for Gaussian distributions).
  
- **Factorization**: Decompose joint distributions into smaller, manageable factors (e.g., using factor graphs).

**Methods**:

- **Conditional Independence**: Exploit conditional independence assumptions to simplify distributions.
  
- **Sparse Representations**: Use sparse matrices or data structures to store conditional probabilities efficiently.

### Approximate Inference in Bayesian Networks

**Problem**:

- **Intractability**: Exact inference in large Bayesian networks is computationally expensive.
  
- **Approximate Methods**: Seek to balance accuracy and computational feasibility.

**Approaches**:

- **Sampling Methods**: Use Monte Carlo techniques (e.g., Markov Chain Monte Carlo) to approximate posterior distributions.
  
- **Variational Inference**: Approximate complex posterior distributions with simpler distributions, optimizing a divergence measure.

**Trade-offs**:

- **Accuracy vs. Speed**: Approximate methods sacrifice accuracy for faster computation.
  
- **Convergence**: Ensure algorithms converge to valid solutions despite approximations.

### Relational and First-Order Probability

**Definition**:

- **Relational Probability**: Extends probability theory to handle uncertainty in relational data and dependencies between entities.
  
- **First-Order Probability**: Integrates logical and probabilistic reasoning, combining predicate logic with probability distributions.

**Applications**:

- **Knowledge Representation**: Model complex relationships and dependencies in relational databases.
  
- **Uncertain Reasoning**: Infer uncertain outcomes based on relational data patterns and logical rules.

**Methods**:

- **Probabilistic Relational Models (PRMs)**: Extend Bayesian networks to relational domains, capturing dependencies between entities.
  
- **Markov Logic Networks (MLNs)**: Integrate logic and probability, allowing for probabilistic reasoning over relational structures.
