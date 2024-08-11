- Structural Representations
- Automata and Complexity
- Central Concepts of Automata Theory
- **Alphabets**, Strings, *Languages*, Problems
- Nondeterministic Finite Automata (NFA)
	- Formal Definition
	- Application: Text Search
	- NFA with Epsilon-Transitions
- Deterministic Finite Automata (DFA)
    - Definition of DFA
    - Processing Strings by DFA
    - Language of DFA
    - Conversion of NFA with €-transitions to NFA without €-transitions
    - Conversion of NFA to DFA

- **Automata Theory Overview**
  - Definition: Study of abstract computing devices or machines.
  - Objective: Define the capabilities and limitations of computing machines.
  - Historical Roots: Emerged in the 20th Century, inspired by mathematicians' efforts to mimic human-like computation.
  
- **Concept of Automata**
  - Definition: Abstract machines imitating certain human features to perform calculations efficiently.
  - Significance: Provides insights into machine computation and problem-solving processes.
  
- **Components of Automata**
  - Abstract Machines: Devices performing computations by transitioning through states.
  - Input-Output Relationship: Abstract machines take inputs and produce outputs based on their state transitions.
  
- **Example: Switch**
  - Illustration of Abstract Machine: Switch transitioning between "off" and "on" states based on push action.
  - Representation: State transitions modelled to reflect input-output dynamics.

- **Finite Automata Introduction**
  - Definition: Abstract machines used for implementing algorithms efficiently.
  - Finite States: Implementations with a limited number of states termed as Finite Automata.
  
- **Applications of Finite Automata**
  1. Designing and checking digital circuit behaviors.
  2. Lexical analysis in compilers, breaking code into logical units.
  3. Scanning large text bodies for patterns, like web page collections.
  4. Verifying systems with finite states, such as communication protocols.

- **Characteristics of Finite Automata**
  - Finite State Constraint: Operates within a finite number of states.
  - State Functionality: Each state retains relevant system history.
  - Resource Efficiency: Fixed resources implementation due to finite states.

- **Example: Finite Automata with Switch**
  - Illustration: Switch functioning as a Finite Automata with "ON" and "off" states.
  - User Interaction: Button press transitions between states, demonstrating finite state behavior.

- **Finite Automaton Behavior**
  - Switch State Dependency: Button behavior varies based on the switch state.
    - "off" State: Button press transitions to "ON" state.
    - "ON" State: Button press transitions to "off" state.

- **Finite Automaton Representation**
  - Visual Model: States depicted as circles ("off" and "ON"), arcs represent transitions labeled "push."
  - Transition Logic: Regardless of state, button push triggers transition to the opposite state.

- **Structural Representation of Finite Automata (FA)**
  - Components: Finite memory (input tape), finite set of states, read-only head, transition function, initial state, final states.
  - Input Tape: Divided into cells containing symbols from the alphabet.
  - Tape Indicators: Symbol 'p' marks the leftmost cell, '$' marks the rightmost, indicating tape boundaries.
  - Head Functionality: Reads one symbol at a time, controlled by finite control, moves left-to-right or right-to-left, one cell at a time.

- **Limitations of Finite Automata**
  - Inability to Remember: FA lacks memory of previous symbols read.
  - Example: Processing string "abc", FA can't recall previously read symbols.

# Automata and Complexity

Automata are essential for the study of computation and complexity. They help in understanding the limits of what a computer can achieve. This study encompasses two main questions:

1. **What can a computer do at all?** This inquiry is termed decidability. The problems that can be solved by a computer are referred to as 'decidable'.

2. **What can a computer do efficiently?** This question delves into intractability. Problems that can be solved by a computer within a time frame no greater than some polynomially growing function of the size of the input are labeled as 'tractable'.

# The Central Concepts of Automata Theory

- **Alphabet**: An alphabet, denoted by Σ, is a finite, non-empty set of symbols.
   Examples:
   1. Σ = {0, 1} is the binary alphabet.
   2. Σ = {a, b, c} is a set of lowercase letters.
   3. Σ = {A, B, C} is a set of uppercase letters.
   4. Σ = set of all ASCII characters.

- **String**: A string is a finite collection of symbols chosen from an alphabet.
   Examples:
   - "00101" is a string in the set of binary alphabet (Σ = {0, 1}).
   - "abcaabd" is a string in the set of lowercase alphabet (Σ = {a, b, c}).

- **Empty String**: Denoted by 'ε', it has zero occurrences of symbols, and its length is zero.

- **Length of a String**: The length of a string is the number of symbols it contains. If 's' is a string, its length is denoted by |s|.
   Examples:
   1. If s = "abbc", then |s| = 4.
   2. Empty string 'ε' has length zero.

- **Powers of an Alphabet**: If Σ is an alphabet, we can express the set of all strings of a certain length using exponential notation.
   Examples:
   - If Σ = {a, b, c}, then Σ^2 = {aa, bb, cc, ab, ba, ca, bc, cb, ac}.
   - Σ^3 = {aaa, bbb, ccc, aab, aac, abb, abc, baa, bac, bbb, bcb, bcc, caa, cab, cac, cba, cbb, cbc, cca, ccb, ccc}.

- **Kleene Closure (Star Closure)**: Denoted by Σ*, it represents the set of all strings over an alphabet Σ including the empty string ε.
   Example:
   - If Σ = {a, b}, then Σ* = {ε, a, b, aa, bb, ab, ba, ...}.

- **Positive Closure**: Denoted by Σ^+, it excludes the empty string from the set of strings.
   Example:
   - If Σ = {a, b}, then Σ^+ = {a, b, aa, bb, ab, ba, ...}.

# Concatenation of Strings

Let 'x' and 'y' be any strings. Then 'xy' denotes the concatenation of 'x' and 'y'.
   
   Example:
   - Let x = "1101" and y = "0011", then xy = "11010011" and yx = "00111101".

## Language

A language is a set of all strings over an alphabet. If Σ is an alphabet and L is a language over Σ, then:

   Example:
   1. The language of all strings consisting of n '0's followed by n '1's is: {ε, 01, 0011, 01111, ...} for some n ≥ 0.
   2. The set of strings of '0's and '1's with an equal number of each: L = {ε, 01, 0011, 000111, 1001, 011}.
   3. The set of binary numbers whose value is a prime: L = {10, 11, 101, 111, 1011, ...}.
   4. Σ* is a language for any alphabet Σ.
   5. ∅ (empty set) is an empty language over any alphabet.
   6. {ε}, the language consisting only of the empty string, is also a language over any alphabet. Note that {ε} ⊆ Σ*.
