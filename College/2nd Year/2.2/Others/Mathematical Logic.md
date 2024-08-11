# UNIT-I: Mathematical Logic

## Statements and Notations

- A proposition or statement is a declarative sentence that is either true or false (but not both).
  - Examples:
    - Paris is in France (true)
    - London is in Denmark (false)
    - - 2 < 4 (true)
    - 4 = 7 (false)
- Not all sentences are propositions:
  - What is your name? (question)
  - Do your homework (command)
  - This sentence is false (neither true nor false)
  - x is an even number (depends on x)
  - Socrates (not even a sentence)
- The truth or falsehood of a proposition is called its truth value.

## Connectives

Connectives are used for making compound propositions. The main ones are:

- `not`
- Conjunction
- Disjunction
- Conditional
- Biconditional

### Truth Tables

#### Logical Negation

- Logical negation produces a value of true if its operand is false and vice versa.
- Truth table for NOT p (¬p or ~p):

| p   | ¬p  |
| --- | --- |
| T   | F   |
| F   | T   |

#### Logical Conjunction

- Logical conjunction produces true if both operands are true.
- Truth table for p AND q (p ∧ q, p & q, or p q):

| p   | q   | p ∧ q |
| --- | --- | ----- |
| T   | T   | T     |
| T   | F   | F     |
| F   | T   | F     |
| F   | F   | F     |

#### Logical Disjunction

- Logical disjunction produces true if at least one operand is true.
- Truth table for p OR q (p ∨ q, p || q, or p + q):

| p   | q   | p ∨ q |
| --- | --- | ----- |
| T   | T   | T     |
| T   | F   | T     |
| F   | T   | T     |
| F   | F   | F     |

#### Logical Implication

- Logical implication produces false only if the first operand is true and the second is false.
- Truth table for p → q:

| p   | q   | p → q |
| --- | --- | ----- |
| T   | T   | T     |
| T   | F   | F     |
| F   | T   | T     |
| F   | F   | T     |

# Mathematical Logic

## Introduction

Mathematical logic is the study of formal systems in relation to symbolic representations and their implications in mathematics. It includes the study of statements, connectives, and the rules of inference.

## Statements and Notation

- **Statement**: A statement is a declarative sentence that is either true or false.
- **Notation**: Statements are often denoted by lowercase letters such as $p, q, r$.
- **Examples**: 
    - $p$: It is raining.
    - $q$: The sun is shining.

## Connectives

- **Conjunction**: $p \land q$ (read as "p and q")
- **Disjunction**: $p \lor q$ (read as "p or q")
- **Negation**: $\neg p$ (read as "not p")
- **Implication**: $p \to q$ (read as "if p then q")
- **Biconditional**: $p \leftrightarrow q$ (read as "p if and only if q")

## Normal Forms

### Conjunctive Normal Form (CNF)

A formula is in Conjunctive Normal Form (CNF) if it is a conjunction (AND) of one or more disjunctions (OR) of literals. A literal is a variable or its negation.

- **Formula**: 

    The general form of a formula in CNF is:
    $(L_{11} \lor L_{12} \lor \ldots \lor L_{1n}) \land (L_{21} \lor L_{22} \lor \ldots \lor L_{2m}) \land \ldots \land (L_{k1} \lor L_{k2} \lor \ldots \lor L_{kl})$
    
    Where $L_{ij}$ is a literal, either a variable or its negation.

- **Example**:

    $(p \lor q) \land (\neg r \lor s \lor t) \land (u)$
    
    In this example, each set of parentheses contains a disjunction of literals, and the entire formula is a conjunction of these disjunctions.

### Disjunctive Normal Form (DNF)

A formula is in Disjunctive Normal Form (DNF) if it is a disjunction (OR) of one or more conjunctions (AND) of literals. 

- **Formula**:

    The general form of a formula in DNF is:
    $(L_{11} \land L_{12} \land \ldots \land L_{1n}) \lor (L_{21} \land L_{22} \land \ldots \land L_{2m}) \lor \ldots \lor (L_{k1} \land L_{k2} \land \ldots \land L_{kl})$
    
    Where $L_{ij}$ is a literal, either a variable or its negation.

- **Example**:

    $(p \land q) \lor (\neg r \land s \land t) \lor (u \land v)$
    
    In this example, each set of parentheses contains a conjunction of literals, and the entire formula is a disjunction of these conjunctions.

## Theory of Inference for the Statement Calculus

- **Modus Ponens**: From $p$ and $p \to q$, infer $q$:
    $p, p \to q \vdash q$
- **Modus Tollens**: From $\neg q$ and $p \to q$, infer $\neg p$:
    $\neg q, p \to q \vdash \neg p$
- **Rules of Inference**: Several rules of inference, such as Hypothetical Syllogism, Disjunctive Syllogism, and others, can be used in logical proofs.

## The Predicate Calculus

- **Quantifiers**:
    - **Universal quantifier**: $\forall x \, P(x)$ (read as "for all x, P(x)")
    - **Existential quantifier**: $\exists x \, P(x)$ (read as "there exists x such that P(x)")
- **Terms**:
    - Terms can be variables, constants, or functions applied to terms.
- **Predicates**:
    - A predicate is a function that returns true or false.

## Inference Theory of the Predicate Calculus

- **Generalization**: From $P(c)$, infer $\forall x \, P(x)$:
    $P(c) \vdash \forall x \, P(x)$
- **Existential Instantiation**: From $\exists x \, P(x)$, infer $P(c)$ for some constant $c$:
    $\exists x \, P(x) \vdash P(c)$
- **Quantifier Negation**: Negating a universal or existential quantifier:
    - $\neg \forall x \, P(x) \equiv \exists x \, \neg P(x)$
    - $\neg \exists x \, P(x) \equiv \forall x \, \neg P(x)$

