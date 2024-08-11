## Push Down Automata
### Definition of Pushdown Automaton (PDA)
A **Pushdown Automaton (PDA)** is a type of automaton that employs a stack to provide additional memory beyond the finite amount available in its state transitions. A PDA can be formally defined as a 7-tuple:

$\text{PDA} = (Q, \Sigma, \Gamma, \delta, q_0, Z_0, F)$

where:
- $Q$ is a finite set of states.
- $\Sigma$ is a finite set of input symbols (input alphabet).
- $\Gamma$ is a finite set of stack symbols (stack alphabet).
- $\delta$ is the transition function, defined as:
 $\delta : Q \times (\Sigma \cup \{\epsilon\}) \times \Gamma \rightarrow \mathcal{P}(Q \times \Gamma^*)$
  This means $\delta$ takes a state, an input symbol (or epsilon for empty string), and a stack symbol, and returns a set of possible next states and stack actions.
- $q_0$ is the initial state.
- $Z_0$ is the initial stack symbol.
- $F$ is the set of accepting states.

### Languages of a PDA
The language accepted by a PDA can be defined in two ways:

1. **Acceptance by Final State**: A PDA accepts a string if, after reading the entire string, it reaches a final state.
2. **Acceptance by Empty Stack**: A PDA accepts a string if, after reading the entire string, the stack is empty.

#### Acceptance by Final State
A string $w \in \Sigma^*$ is accepted by a PDA if, starting from the initial configuration $(q_0, w, Z_0)$, it reaches a configuration $(q_f, \epsilon, \gamma)$ where $q_f \in F$ (a final state), $\epsilon$ denotes the empty input, and $\gamma$ is any stack content.

#### Acceptance by Empty Stack
A string $w \in \Sigma^*$ is accepted by a PDA if, starting from the initial configuration $(q_0, w, Z_0)$, it reaches a configuration $(q, \epsilon, \epsilon)$ where $\epsilon$ denotes the empty input and empty stack.

### Equivalence of PDA and Context-Free Grammars (CFG)
PDAs and CFGs are equivalent in terms of the languages they can generate. Specifically, for every context-free language, there exists a PDA that accepts it, and vice versa.

#### From CFG to PDA
Given a CFG, a PDA can be constructed to accept the same language. The PDA simulates the derivation of the CFG by using the stack to keep track of the non-terminals and terminals.

#### From PDA to CFG
Given a PDA, a CFG can be constructed that generates the same language. The non-terminals in the CFG correspond to the states and stack symbols of the PDA.

### Acceptance by Final State
Acceptance by final state in a PDA can be formally described using configurations and transitions. A configuration of a PDA is a tuple $(q, w, \gamma)$ where $q$ is the current state, $w$ is the remaining input string, and $\gamma$ is the current stack content.

A PDA accepts a string by final state if there exists a sequence of transitions that leads from the initial configuration $(q_0, w, Z_0)$ to a configuration $(q_f, \epsilon, \gamma)$ where $q_f \in F$.

#### Example
Consider a PDA that accepts the language $L = \{a^n b^n \mid n \geq 0\}$:
- $Q = \{q_0, q_1, q_2\}$
- $\Sigma = \{a, b\}$
- $\Gamma = \{Z_0, X\}$
- $q_0$ is the initial state.
- $Z_0$ is the initial stack symbol.
- $F = \{q_2\}$

Transition function $\delta$:
- $\delta(q_0, a, Z_0) = \{(q_0, XZ_0)\}$
- $\delta(q_0, a, X) = \{(q_0, XX)\}$
- $\delta(q_0, b, X) = \{(q_1, \epsilon)\}$
- $\delta(q_1, b, X) = \{(q_1, \epsilon)\}$
- $\delta(q_1, \epsilon, Z_0) = \{(q_2, Z_0)\}$

This PDA pushes an $X$ onto the stack for every $a$ read in state $q_0$, and pops an $X$ from the stack for every $b$ read in state $q_1$. If the stack is empty after all input has been read, the PDA transitions to the final state $q_2$ and accepts the string.

---

## Introduction to Turing Machine

A **Turing Machine (TM)** is a mathematical model of computation that defines an abstract machine capable of simulating any algorithm. It was invented by Alan Turing in 1936 and is used to understand the limits of what can be computed. A Turing machine manipulates symbols on a strip of tape according to a set of rules.

### Formal Description

A Turing machine can be formally described as a 7-tuple:

\[ \text{TM} = (Q, \Sigma, \Gamma, \delta, q_0, q_{\text{accept}}, q_{\text{reject}}) \]

where:
- $Q$ is a finite set of states.
- $\Sigma$ is a finite set of input symbols (input alphabet), not including the blank symbol $\sqcup$.
- $\Gamma$ is a finite set of tape symbols (tape alphabet), where $\Sigma \subseteq \Gamma$ and $\sqcup \in \Gamma$ (the blank symbol $\sqcup$).
- $\delta$ is the transition function:
  \[
  \delta : Q \times \Gamma \rightarrow Q \times \Gamma \times \{L, R\}
  \]
  This means $\delta$ takes a state and a tape symbol, and returns a new state, a new tape symbol, and a direction (left $L$ or right $R$).
- $q_0$ is the initial state.
- $q_{\text{accept}}$ is the accept state.
- $q_{\text{reject}}$ is the reject state, where $q_{\text{accept}} \neq q_{\text{reject}}$.

### Instantaneous Description

An **instantaneous description (ID)** of a Turing machine is a snapshot of the machine's current status. It includes the current state, the current tape content, and the position of the tape head. An ID can be represented as:

\[ (q, \alpha \, a \, \beta) \]

where:
- $q$ is the current state.
- $\alpha$ is the tape content to the left of the head.
- $a$ is the symbol under the tape head.
- $\beta$ is the tape content to the right of the head.

For example, if the tape content is $\ldots 0011011 \ldots$, the head is on the first '1', and the machine is in state $q_5$, the ID is $(q_5, 001 \, 1 \, 011)$.

### Language of a Turing Machine

The **language of a Turing machine** is the set of all strings that the machine accepts. A Turing machine $TM$ accepts a string $w \in \Sigma^*$ if, starting from the initial configuration $(q_0, \sqcup w \sqcup, 0)$, it eventually reaches the accept state $q_{\text{accept}}$.

Formally, the language $L(TM)$ accepted by a Turing machine $TM$ is defined as:

\[ L(TM) = \{ w \in \Sigma^* \mid TM \text{ accepts } w \} \]

### Example

Consider a Turing machine that decides the language $L = \{0^n 1^n \mid n \geq 0\}$:

- $Q = \{q_0, q_1, q_2, q_{\text{accept}}, q_{\text{reject}}\}$
- $\Sigma = \{0, 1\}$
- $\Gamma = \{0, 1, X, \sqcup\}$
- $q_0$ is the initial state.
- $q_{\text{accept}}$ is the accept state.
- $q_{\text{reject}}$ is the reject state.

Transition function $\delta$:
- $\delta(q_0, 0) = (q_1, X, R)$
- $\delta(q_1, 0) = (q_1, 0, R)$
- $\delta(q_1, 1) = (q_2, X, L)$
- $\delta(q_2, 0) = (q_2, 0, L)$
- $\delta(q_2, X) = (q_0, X, R)$
- $\delta(q_0, 1) = (q_{\text{accept}}, 1, R)$
- $\delta(q_0, X) = (q_{\text{accept}}, X, R)$

This Turing machine starts by replacing the leftmost 0 with X, moves right to find the rightmost 1, replaces it with X, and moves left to find the next 0. If it finds all symbols replaced by X and no mismatches, it accepts the input string.

---
## Undecidability

**Undecidability** refers to the property of certain decision problems which cannot be resolved by any algorithm. In formal terms, a decision problem is undecidable if there is no Turing machine that can always give a correct yes-or-no answer to the problem for all inputs.

### A Language that is Not Recursively Enumerable

A language is **recursively enumerable (RE)** if there is a Turing machine which will enumerate all strings in the language. In other words, a Turing machine will accept all strings in the language and will either reject or run forever on strings not in the language.

A language $L$ is **not recursively enumerable (not RE)** if there is no Turing machine that can list all and only the strings in $L$. 

#### Example of a Not RE Language

Consider the language $L_{\text{nonRE}}$ which is defined as follows:
\[ L_{\text{nonRE}} = \{ \langle M \rangle \mid M \text{ is a Turing machine and } L(M) \text{ is not recursively enumerable} \} \]

This language contains descriptions of Turing machines whose languages are not recursively enumerable. There is no Turing machine that can decide $L_{\text{nonRE}}$ because the problem of determining whether a Turing machine's language is not RE is undecidable.

### Undecidable Problems about Turing Machines

There are several fundamental problems concerning Turing machines that are undecidable. These include:

1. **The Halting Problem**
   - **Problem:** Given a Turing machine $M$ and an input $w$, determine whether $M$ halts on $w$.
   - **Undecidability:** Alan Turing proved that there is no Turing machine that can solve the halting problem for all possible inputs.

2. **The Membership Problem**
   - **Problem:** Given a Turing machine $M$ and a string $w$, determine whether $w$ is in the language $L(M)$ accepted by $M$.
   - **Undecidability:** This problem is also undecidable because it can be reduced to the halting problem.

3. **The Emptiness Problem**
   - **Problem:** Given a Turing machine $M$, determine whether $L(M) = \emptyset$ (i.e., whether $M$ accepts no strings).
   - **Undecidability:** This problem is undecidable because it is impossible to determine if there exists any string that $M$ will accept.

4. **The Equivalence Problem**
   - **Problem:** Given two Turing machines $M_1$ and $M_2$, determine whether $L(M_1) = L(M_2)$.
   - **Undecidability:** This problem is undecidable because it is impossible to determine whether two Turing machines accept exactly the same language.

### Example: The Halting Problem

The **halting problem** is one of the most famous undecidable problems. It can be formally stated as follows:

- **Input:** A Turing machine $M$ and an input string $w$.
- **Question:** Does $M$ halt when run on $w$?

Alan Turing proved that there is no general algorithm that solves the halting problem for all possible Turing machine-input pairs. The proof uses a technique known as diagonalization and is a classic example of a proof by contradiction.

### Proof Sketch of the Halting Problem's Undecidability

1. Assume that there exists a Turing machine $H$ that decides the halting problem. This means $H$ takes as input a pair $\langle M, w \rangle$ and returns "yes" if $M$ halts on $w$, and "no" otherwise.
2. Construct a new Turing machine $D$ that uses $H$ as a subroutine:
   - $D$ takes as input a description of a Turing machine $\langle M \rangle$.
   - $D$ simulates $H(\langle M, \langle M \rangle \rangle)$:
     - If $H$ says $M$ halts on $\langle M \rangle$, then $D$ enters an infinite loop.
     - If $H$ says $M$ does not halt on $\langle M \rangle$, then $D$ halts.
3. Now consider what happens when $D$ is given its own description as input: $D(\langle D \rangle)$.
   - If $D$ halts on $\langle D \rangle$, then by construction, $D$ should enter an infinite loop, which is a contradiction.
   - If $D$ does not halt on $\langle D \rangle$, then by construction, $D$ should halt, which is also a contradiction.

This contradiction shows that no such Turing machine $H$ can exist, proving that the halting problem is undecidable.

---

