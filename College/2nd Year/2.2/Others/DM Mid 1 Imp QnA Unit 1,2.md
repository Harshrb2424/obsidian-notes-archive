### 1. Logical Equivalence

Prove that: $( p \to q) \land ( p \to r) \leftrightarrow p \to ( q \land r)$ are logically equivalent.

| $p$ | $q$ | $r$ | $p \to q$ | $p \to r$ | $( p \to q) \land ( p \to r)$ | $p \to (q \land r)$ |
| --- | --- | --- | --------- | --------- | ----------------------------- | ------------------- |
| T   | T   | T   | T         | T         | T                             | T                   |
| T   | T   | F   | T         | F         | F                             | F                   |
| T   | F   | T   | F         | T         | F                             | F                   |
| T   | F   | F   | F         | F         | F                             | F                   |
| F   | T   | T   | T         | T         | T                             | T                   |
| F   | T   | F   | T         | T         | T                             | T                   |
| F   | F   | T   | T         | T         | T                             | T                   |
| F   | F   | F   | T         | T         | T                             | T                   |


Hence,

| $( p \to q) \land ( p \to r)$ | $p \to (q \land r)$ |$( p \to q) \land ( p \to r) \leftrightarrow p \to ( q \land r)$|
| ----------------------------- | ------------------- |---------------------|
| T                             | T                   |T|
| F                             | F                   |T|
| F                             | F                   |T|
| F                             | F                   |T|
| T                             | T                   |T|
| T                             | T                   |T|
| T                             | T                   |T|
| T                             | T                   |T|
So, the truth tables confirm the equivalence $( p \to q) \land ( p \to r) \leftrightarrow p \to ( q \land r).$ is logically equivalent.
### 2. Prenex Conjunctive Normal Form (PCNF)
Obtain the PCNF for the propositional function: $(\neg p \lor \neg q) \to ( p \leftrightarrow q)$

![[Pasted image 20240427211538.png]]

#### OR

Propositional function: $(\neg p \lor \neg q) \to ( p \leftrightarrow q)$

| $p$ | $q$ | $\neg p$ | $\neg q$ | $\neg p \lor \neg q$ | $p \leftrightarrow q$ | $(\neg p \lor \neg q) \to ( p \leftrightarrow q)$ |
|----|----|-------|-------|--------------------|----------------|------------------------------------------------|
| T  | T  | F     | F     | F                  | T              | T                                               |
| T  | F  | F     | T     | T                  | F              | F                                               |
| F  | T  | T     | F     | T                  | F              | F                                               |
| F  | F  | T     | T     | T                  | T              | T                                               |
To obtain the Principal Conjunctive Normal Form (PCNF) of the propositional function $(\neg p \lor \neg q) \to ( p \leftrightarrow q)$, we first need to use a truth table to determine when the function is false. Then, we use the conditions where the function is false to construct the PCNF.

#### Truth Table

First, let's create a truth table for the propositional function $(\neg p \lor \neg q) \to (p \leftrightarrow q)$:

| $p$ | $q$ | $\neg p$ | $\neg q$ | $\neg p \lor \neg q$ | $p \leftrightarrow q$ | $(\neg p \lor \neg q) \to ( p \leftrightarrow q)$ |
|----|----|-------|-------|--------------------|----------------|------------------------------------------------|
| T  | T  | F     | F     | F                  | T              | T                                               |
| T  | F  | F     | T     | T                  | F              | F                                               |
| F  | T  | T     | F     | T                  | F              | F                                               |
| F  | F  | T     | T     | T                  | T              | T                                               |

The function $(\neg p \lor \neg q) \to (p \leftrightarrow q)$ is false in two cases:

1. When $p = T$ and $q = F$.
2. When $p = F$ and $q = T$.

Therefore, the PCNF of the propositional function $(\neg p \lor \neg q) \to ( p \leftrightarrow q)$ is:

$$ (p \lor \neg q) \land (\neg p \lor q) $$
### 3. Prenex Disjunctive Normal Form (PDNF)

Obtain the PDNF of: $( P \land Q) \lor (\neg P \land R) \lor (Q \land R)$
![[WhatsApp Image 2024-04-26 at 19.32.17_39f29ca6.jpg]]
### 4. PCNF

Obtain the PCNF of: $(P  \to (Q \land R)) \land ( \neg P \to (\neg Q \land \neg R))$

![[WhatsApp Image 2024-04-26 at 19.35.27_014be98c.jpg]]
### 5. Symbolize the following argument:

- All men are giants.
- Not all birds can fly.
- Some babies are illogical.
- There is a student who likes maths but not history.

To symbolize the argument, you can express each statement as follows:

1. "All men are giants."  
   Let:
   - $M(x)$: $x$ is a man.
   - $G(x)$: $x$ is a giant.
   Quantifier:  
   $\forall x (M(x) \rightarrow G(x))$

2. "Not all birds can fly."  
   Let:
   - $B(x)$: $x$ is a bird.
   - $F(x)$: $x$ can fly.
   Quantifier:  
   $\exists x (B(x) \wedge \neg F(x))$

3. "Some babies are illogical."  
   Let:
   - $B(x)$: $x$ is a baby.
   - $I(x)$: $x$ is illogical.
   Quantifier:  
   $\exists x (B(x) \wedge I(x))$

4. "There is a student who likes maths but not history."  
   Let:
   - $S(x)$: $x$ is a student.
   - $Lm(x)$: $x$ likes maths.
   - $Lh(x)$: $x$ likes history.
   Quantifier:  
   $\exists x (S(x) \wedge Lm(x) \wedge \neg Lh(x))$
These symbolic statements represent the given arguments using predicates and quantifiers.

### 6. Warshall's Algorithm

Compute the transitive closure of a relation $R = {(1,2), (2,1), (2,3), (3,4), (4,1)}$ defined on the set $A = \{1,2,3,4\}$.

![[WhatsApp Image 2024-04-27 at 21.47.07_a8109c58.jpg]]![[WhatsApp Image 2024-04-27 at 21.47.07_83af7ceb.jpg]]

 the transitive closure of which is the maximal relation:
{(1,1), (1, 2), (1,3), (1,4), (2,1), (2, 2), (2,3), (2,4), (3,1), (3, 2), (3,3), (3,4), (4,1), (4, 2), (4,3), (4,4)}
Therefore, the transitive closure of the initial relation will be also the maximal relation.
### 7. Hasse Diagram

Draw the Hasse diagram for the poset $( P(S), \subseteq )$, where $P(S)$ is the power set on $S = \{a, b, c\}$.

The power set of $S$ is:

$$\mathcal{P}(S) = \{\emptyset, \{a\}, \{b\}, \{c\}, \{a, b\}, \{a, c\}, \{b, c\}, \{a, b, c\}\}$$


![](https://i.stack.imgur.com/1wAHc.png)

### 8. Determine the Bijection

Determine whether each of these functions is a bijection from $\mathbb{R}$ to $\mathbb{R}$:
- $f(x) = -3x + 4$
- $f(x) = -3x^2 + 7$

#### 1. $f(x) = -3x + 4$

**Injectivity (one-to-one):**
A function is injective if different inputs yield different outputs. We check if $f(x_1) = f(x_2)$ implies $x_1 = x_2$.

Given $f(x) = -3x + 4$, if $f(x_1) = f(x_2)$, then:
$$-3x_1 + 4 = -3x_2 + 4$$
Simplifying:
$$-3x_1 = -3x_2$$
$$x_1 = x_2$$

Therefore, the function is injective.

**Surjectivity (onto):**
A function is surjective if every element in the codomain has a pre-image in the domain. For $f(x) = -3x + 4$, we want to find out if, for every $y \in \mathbb{R}$, there is an $x \in \mathbb{R}$ such that $f(x) = y$.

Given $f(x) = y$, we have:
$$-3x + 4 = y$$
$$x = \frac{y - 4}{-3}$$

For every $y \in \mathbb{R}$, there exists an $x \in \mathbb{R}$ that satisfies the equation. Therefore, the function is surjective.

**Conclusion:** Since the function $f(x) = -3x + 4$ is both injective and surjective, it is a bijection from $\mathbb{R}$ to $\mathbb{R}$.

#### 2. $f(x) = -3x^2 + 7$

**Injectivity (one-to-one):**
A function is injective if different inputs yield different outputs. We check if $f(x_1) = f(x_2)$ implies $x_1 = x_2$.

Given $f(x) = -3x^2 + 7$, if $f(x_1) = f(x_2)$, then:
$$-3x_1^2 + 7 = -3x_2^2 + 7$$
Simplifying:
$$-3x_1^2 = -3x_2^2$$
$$x_1^2 = x_2^2$$

From the above, we know that $x_1 = \pm x_2$. Therefore, the function is not injective because different values of $x_1$ and $x_2$ (e.g.,$(x_1 = 1$ and $x_2 = -1$) can yield the same output.

**Surjectivity (onto):**
A function is surjective if every element in the codomain has a pre-image in the domain. For $f(x) = -3x^2 + 7$, we want to find out if, for every $y \in \mathbb{R}$, there is an $x \in \mathbb{R}$ such that $f(x) = y$.

Given $f(x) = y$, we have:
$$-3x^2 + 7 = y$$
$$-3x^2 = y - 7$$
$$x^2 = \frac{y - 7}{-3}$$

The right-hand side of the equation must be non-negative, which implies:
$$y - 7 \geq 0$$

This condition is equivalent to:
$$y \leq 7$$

Therefore, the function is not surjective because not every element in $\mathbb{R}$ (specifically $y > 7$) has a pre-image in $\mathbb{R}$.

**Conclusion:** Since the function $f(x) = -3x^2 + 7$ is neither injective nor surjective, it is not a bijection from $\mathbb{R}$ to $\mathbb{R}$.
### 9. Hasse Diagram

Construct the Hasse diagram representing the positive divisors of 36.

- Positive divisors of 36 are the numbers that divide 36 without leaving a remainder. These divisors are: 1,2,3,4,6,9,12,18,361,2,3,4,6,9,12,18,36.

![](https://slideplayer.com/slide/16484689/96/images/20/1.Draw+the+Hasse+Diagram+for+Representing+the+positive+divisors+of+36..jpg)
### 10. Congruence Modulo

Show that congruence modulo m is an equivalence relation on integers.

To show that congruence modulo $m$ is an equivalence relation on integers, we need to demonstrate that it satisfies the three properties of an equivalence relation:

1. **Reflexivity**: An integer $a$ is congruent to itself modulo $m$. That is, $a \equiv a \pmod{m}$.

2. **Symmetry**: If an integer $a$ is congruent to another integer $b$ modulo $m$, then $b \equiv a \pmod{m}$.

3. **Transitivity**: If an integer $a$ is congruent to another integer $b$ modulo $m$, and $b$ is congruent to another integer $c$ modulo $m$, then $a \equiv c \pmod{m}$.

#### 1. Reflexivity

For any integer $a$, $a - a = 0$, which is divisible by $m$. Therefore, $a \equiv a \pmod{m}$. Thus, the congruence is reflexive.

#### 2. Symmetry

If $a \equiv b \pmod{m}$, then $m \mid (a - b)$. This means $m \mid (b - a)$, which implies $b \equiv a \pmod{m}$. Therefore, congruence modulo $m$ is symmetric.

#### 3. Transitivity

If $a \equiv b \pmod{m}$, and $b \equiv c \pmod{m}$, then:
- $m \mid (a - b)$, and
- $m \mid (b - c)$.

Adding these two congruences gives:
- $m \mid ((a - b) + (b - c)) = m \mid (a - c)$.

Therefore, $a \equiv c \pmod{m}$, and congruence modulo $m$ is transitive.

### 11. Verify the Validity

Verify the validity of the following inference:

- All integers are rational numbers.
- Some integers are powers of 2.
- Therefore, some rational numbers are powers of 2.

#### Premises:

1. **"All integers are rational numbers."**
    Let:
    - $I(x)$ represents "x is an integer."
    - $R(x)$ represents "x is a rational number."
    This statement implies that every integer $x$ is also a rational number.
    **Universal quantifier:**
        $\forall x \, (I(x) \to R(x))$
2. **"Some integers are powers of 2."**
    Let:
    - $I(x)$ represents "x is an integer."
    - $P(x)$ represents "x is a power of 2."
    This statement implies that there exists an integer $x$ that is a power of 2.
    **Existential quantifier:**
        $\exists x \, (I(x) \land P(x))$

#### Conclusion:

- **"Therefore, some rational numbers are powers of 2."** 
    Let:
    - $R(x)$ represents "x is a rational number."
    - $P(x)$ represents "x is a power of 2."
    This statement implies that there exists a rational number $x$ that is a power of 2.
    **Existential quantifier:**
        $\exists x \, (R(x) \land P(x))$

#### Verification:
![[WhatsApp Image 2024-04-27 at 21.56.58_dbfb3f15.jpg]]
### 12. Brief Description

- Describe briefly about all connectives.
- Define predicates and quantifiers with an example.

#### Connectives

Connectives are logical operators used to combine or modify statements (propositions) to form more complex statements.
![[WhatsApp Image 2024-04-27 at 21.19.27_94cf6a6b.jpg]]
1. **Negation (¬)**: The negation operator takes one proposition and negates it. For a proposition $p$, the negation is $\neg p$, meaning "not $p$." If $p$ is true, $\neg p$ is false, and vice versa.

2. **Conjunction (∧)**: The conjunction operator combines two propositions. For propositions $p$ and $q$, the conjunction is $p \land q$, meaning "both $p$ and $q$." It is true only when both $p$ and $q$ are true.

3. **Disjunction (∨)**: The disjunction operator combines two propositions. For propositions $p$ and $q$, the disjunction is $p \lor q$, meaning "either $p$ or $q$, or both." It is true when at least one of $p$ or $q$ is true.

4. **Implication (→)**: The implication operator connects two propositions in a conditional relationship. For propositions $p$ and $q$, the implication is $p \to q$, meaning "if $p$, then $q$." It is false only when $p$ is true and $q$ is false.

5. **Biconditional (↔)**: The biconditional operator connects two propositions in a bidirectional relationship. For propositions $p$ and $q$, the biconditional is $p \leftrightarrow q$, meaning "$p$ if and only if $q$." It is true when both propositions have the same truth value.

#### Predicates and Quantifiers
![[Pasted image 20240427212042.png]]
![[Pasted image 20240427212114.png]]
### 13. Group Structure

Show that $( \mathbb{Z}, * )$ is a group where the binary operation $*$ is defined by: $a * b = a + b + 1$

https://www.toppr.com/ask/question/if-be-an-operating-on-z-defined-as-abab1-forall-a-b-in/
or
https://www.quora.com/How-do-I-determine-whether-the-binary-operation-gives-a-group-structureon-let-be-defined-on-Z-by-a-b-ab-a-1
I have no idea.....
### 14. Students and Papers

- 900 students appeared for two papers in Mathematics.
- 740 students passed in Paper I and 660 passed in Paper II.
- If 640 passed in both the papers, then determine the number of students who failed in both the papers.


The total number of students who passed either Paper I, Paper II, or both papers is represented as:
$|A \cup B| = |A| + |B| - |A \cap B|$
Where:
- $|A| = 740$ (the number of students who passed Paper I)
- $|B| = 660$ (the number of students who passed Paper II)
- $|A \cap B| = 640$ (the number of students who passed both Paper I and Paper II)

Now, calculate $|A \cup B|$:
$|A \cup B| = |A| + |B| - |A \cap B|$
$|A \cup B| = 740 + 660 - 640 = 760$

Next, the total number of students who appeared for the papers is 900.

The number of students who failed in both papers can be calculated by subtracting the number of students who passed either paper (or both papers) from the total number of students:
$\text{Students who failed in both papers} = \text{Total students} - |A \cup B| = 900 - 760 = 140$

Therefore, the number of students who failed in both papers is **140**.