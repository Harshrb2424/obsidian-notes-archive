
### 1. Obtain the PDNF and PCNF of the following statement formula: (┐P V ┐Q) → (P ↔ Q)

First, construct the truth table for the formula to determine its values for all possible combinations of $P$ and $Q$.

**Truth Table:**

| $P$ | $Q$ | $\neg P$ | $\neg Q$ | $\neg P \lor \neg Q$ | $P \leftrightarrow Q$ | $(\neg P \lor \neg Q) \to (P \leftrightarrow Q)$ |
|:------:|:------:|:-----------:|:-----------:|:-------------------------:|:-------------------------:|:----------------------------------------------------:|
|   T    |   T    |      F      |      F      |            F              |             T             |                        T                           |
|   T    |   F    |      F      |      T      |            T              |             F             |                        F                           |
|   F    |   T    |      T      |      F      |            T              |             F             |                        F                           |
|   F    |   F    |      T      |      T      |            T              |             T             |                        T                           |

**Principal Disjunctive Normal Form (PDNF)**

The PDNF is a disjunction (OR) of all the minterms where the formula is true.

From the truth table, the formula is true for:

- $(P, Q) = (T, T)$
- $(P, Q) = (F, F)$

**Minterms where the formula is true:**

1. For $(P, Q) = (T, T)$:
   $P \land Q$

2. For $(P, Q) = (F, F)$:
   $\neg P \land \neg Q$

**PDNF:**
$(P \land Q) \lor (\neg P \land \neg Q)$

**Principal Conjunctive Normal Form (PCNF)**

The PCNF is a conjunction (AND) of all the maxterms where the formula is false.

From the truth table, the formula is false for:

- $(P, Q) = (T, F)$
- $(P, Q) = (F, T)$

**Maxterms where the formula is false:**

1. For $(P, Q) = (T, F)$:
   $P \lor Q$

2. For $(P, Q) = (F, T)$:
   $\neg P \lor \neg Q$

**PCNF:**
$(P \lor Q) \land (\neg P \lor \neg Q)$

- **PDNF:** $(P \land Q) \lor (\neg P \land \neg Q)$
- **PCNF:** $(P \lor Q) \land (\neg P \lor \neg Q)$


### 2.a) Proof of Logical Expression

**Question:**

Show that:

$(\exists x) (p(x) \land Q(x)) \Rightarrow (\exists x) (p(x) \land (\exists x) Q(x))$

**Proof:**

To prove this, we need to show that if the antecedent \((\exists x) (p(x) \land Q(x))\) is true, then the consequent \((\exists x) (p(x) \land (\exists x) Q(x))\) must also be true.

1. **Assume the antecedent is true:**

   $(\exists x) (p(x) \land Q(x))$

   This means there exists at least one \(x\) (say \(x_0\)) such that:

   $p(x_0) \land Q(x_0)$

2. **Show that the consequent is true:**

   We need to show that:

   $(\exists x) (p(x) \land (\exists x) Q(x))$

   For the consequent, we can express it as:

   $(\exists x) (p(x) \land (\exists y) Q(y))$

   Given that \(p(x_0) \land Q(x_0)\) is true for some \(x_0\), it implies:

   $p(x_0) \text{ is true}$
   $(\exists y) Q(y) \text{ is true}$ 

   because \(Q(x_0)\) is true, which guarantees that \(Q(y)\) is satisfied for at least \(y = x_0\).

   Hence, we can pick \(x = x_0\) in the consequent:

   $p(x_0) \land (\exists y) Q(y)$

   Therefore:

   $(\exists x) (p(x) \land (\exists y) Q(y))$

   is true.

### 2.b) Symbolize the Argument and Check Validity

**Question:**

Symbolize the following argument and check for its validity:

1. All men are giants.
2. Not all birds can fly.
3. Some babies are illogical.
4. There is a student who likes maths, but not history.

**Solution:**

1. **Symbolize the Statements:**

   - Let $M(x)$: $x$ is a man.
   - Let $G(x)$: $x$ is a giant.
   - Let $B(x)$: $x$ is a bird.
   - Let $F(x)$: $x$ can fly.
   - Let $I(x)$: $x$ is illogical.
   - Let $S(x)$: $x$ is a student.
   - Let $L(x, m)$: $x$ likes $m$.

   **Statements:**

   1. All men are giants.
      $\forall x (M(x) \rightarrow G(x))$

   2. Not all birds can fly.
      $\neg \forall x (B(x) \rightarrow F(x))$
      This is equivalent to:
      $\exists x (B(x) \land \neg F(x))$

   3. Some babies are illogical.
      Let $B(x)$ represent babies as well (assuming $B(x)$ could also represent babies):
      $\exists x (B(x) \land I(x))$

   4. There is a student who likes maths but not history.
      Let $M$ represent maths and $H$ represent history:
      $\exists x (S(x) \land L(x, M) \land \neg L(x, H))$

2. **Check for Validity:**

   To determine validity, we need to check if there is any logical relationship between the statements or if there is a contradiction among them. However, validity checking usually involves constructing truth tables or logical proofs, which can be more complex.

   **Validity Check:**

   The given statements seem independent in nature, and their validity cannot be easily determined without additional context or logical connections. 

   Generally, logical validity in such contexts would involve setting up a formal proof or refutation process, which requires more detailed analysis. 

   To summarize:

   - **Symbolized Statements:**
     1. $\forall x (M(x) \rightarrow G(x))$
     2. $\exists x (B(x) \land \neg F(x))$
     3. $\exists x (B(x) \land I(x))$
     4. $\exists x (S(x) \land L(x, M) \land \neg L(x, H))$

   - **Validity:** 
     The statements are not inherently contradictory, but proving validity requires further formal analysis or context-specific information.

### 3.a) De Morgan's Laws Using Truth Tables

**De Morgan's Laws:**

1. \(\neg (P \land Q) \equiv \neg P \lor \neg Q\)
2. \(\neg (P \lor Q) \equiv \neg P \land \neg Q\)

**Proof Using Truth Tables:**

1. **\(\neg (P \land Q) \equiv \neg P \lor \neg Q\)**

   **Truth Table:**

| \(P\) | \(Q\) | \(P \land Q\) | \(\neg (P \land Q)\) | \(\neg P\) | \(\neg Q\) | \(\neg P \lor \neg Q\) |
|:----:|:----:|:------------:|:-------------------:|:----------:|:----------:|:----------------------:|
|  T   |  T   |      T       |          F          |     F      |     F      |           F            |
|  T   |  F   |      F       |          T          |     F      |     T      |           T            |
|  F   |  T   |      F       |          T          |     T      |     F      |           T            |
|  F   |  F   |      F       |          T          |     T      |     T      |           T            |

   From the truth table, \(\neg (P \land Q)\) and \(\neg P \lor \neg Q\) have the same truth values for all combinations of \(P\) and \(Q\), proving the equivalence.

2. **\(\neg (P \lor Q) \equiv \neg P \land \neg Q\)**

   **Truth Table:**

| \(P\) | \(Q\) | \(P \lor Q\) | \(\neg (P \lor Q)\) | \(\neg P\) | \(\neg Q\) | \(\neg P \land \neg Q\) |
|:----:|:----:|:------------:|:-------------------:|:----------:|:----------:|:----------------------:|
|  T   |  T   |      T       |          F          |     F      |     F      |           F            |
|  T   |  F   |      T       |          F          |     F      |     T      |           F            |
|  F   |  T   |      T       |          F          |     T      |     F      |           F            |
|  F   |  F   |      F       |          T          |     T      |     T      |           T            |

   From the truth table, \(\neg (P \lor Q)\) and \(\neg P \land \neg Q\) have the same truth values for all combinations of \(P\) and \(Q\), proving the equivalence.

### 3.b) Contrapositive, Converse, and Inverse of the Conditional Statement

**Given Statement:**

"If the sky is cloudy, then it will rain or it will not rain."

**Let:**

- \(P\): The sky is cloudy.
- \(Q\): It will rain.

**Original Statement:**

$P \rightarrow (Q \lor \neg Q)$

**Analysis:**

The statement \(Q \lor \neg Q\) is a tautology (always true) because either it will rain or it will not rain.

So, the original statement simplifies to:

$P \rightarrow \text{True}$

which is always true regardless of \(P\). 

**1. Contrapositive:**

The contrapositive of \(P \rightarrow Q\) is \(\neg Q \rightarrow \neg P\).

Here, the contrapositive of \(P \rightarrow \text{True}\) is:

$\neg (\text{True}) \rightarrow \neg P$

Since \(\neg (\text{True})\) is false, the contrapositive simplifies to:

$\text{False} \rightarrow \neg P$

which is always true.

**2. Converse:**

The converse of \(P \rightarrow Q\) is \(Q \rightarrow P\).

For the statement \(P \rightarrow \text{True}\), the converse is:

$\text{True} \rightarrow P$

which is not necessarily true, as it asserts \(P\) without being relevant to the truth of \(\text{True}\).

**3. Inverse:**

The inverse of \(P \rightarrow Q\) is \(\neg P \rightarrow \neg Q\).

For the statement \(P \rightarrow \text{True}\), the inverse is:

$\neg P \rightarrow \neg (\text{True})$

Since \(\neg (\text{True})\) is false, the inverse simplifies to:

$\neg P \rightarrow \text{False}$

which means \(\neg P\) must be false, so \(P\) must be true for the implication to hold. However, this inverse is not necessarily true in general.

- **De Morgan's Laws:**

  1. \(\neg (P \land Q) \equiv \neg P \lor \neg Q\)
  2. \(\neg (P \lor Q) \equiv \neg P \land \neg Q\)

- **For the conditional statement:**

  1. **Contrapositive:** \(\text{False} \rightarrow \neg P\) (always true)
  2. **Converse:** \(\text{True} \rightarrow P\) (not necessarily true)
  3. **Inverse:** \(\neg P \rightarrow \text{False}\) (depends on \(P\))

# 4. To find the **Principal Disjunctive Normal Form (PDNF)** and **Principal Conjunctive Normal Form (PCNF)** for the formula:

$(P \land Q) \lor (\neg P \land R) \lor (Q \land R)$

we'll first construct the truth table and then derive the PDNF and PCNF from it.

### 1. Construct the Truth Table

**Variables:**
- $P$
- $Q$
- $R$

**Formula:**
$F = (P \land Q) \lor (\neg P \land R) \lor (Q \land R)$

**Truth Table:**

| $P$ | $Q$ | $R$ | $P \land Q$ | $\neg P$ | $\neg P \land R$ | $Q \land R$ | $F$ |
|:------:|:------:|:------:|:--------------:|:-----------:|:-------------------:|:--------------:|:------:|
|   T    |   T    |   T    |       T        |      F      |         F           |        T       |   T    |
|   T    |   T    |   F    |       T        |      F      |         F           |        F       |   T    |
|   T    |   F    |   T    |       F        |      F      |         F           |        F       |   F    |
|   T    |   F    |   F    |       F        |      F      |         F           |        F       |   F    |
|   F    |   T    |   T    |       F        |      T      |         T           |        T       |   T    |
|   F    |   T    |   F    |       F        |      T      |         F           |        F       |   F    |
|   F    |   F    |   T    |       F        |      T      |         T           |        F       |   T    |
|   F    |   F    |   F    |       F        |      T      |         F           |        F       |   F    |

### 2. Principal Disjunctive Normal Form (PDNF)

The PDNF is a disjunction (OR) of all the minterms where the formula $F$ is true.

From the truth table, $F$ is true for:

- Row 1: $(P = T, Q = T, R = T)$
- Row 2: $(P = T, Q = T, R = F)$
- Row 5: $(P = F, Q = T, R = T)$
- Row 7: $(P = F, Q = F, R = T)$

**Minterms where the formula is true:**

1. For $(P = T, Q = T, R = T)$:
   $P \land Q \land R$

2. For $(P = T, Q = T, R = F)$:
   $P \land Q \land \neg R$

3. For $(P = F, Q = T, R = T)$:
   $\neg P \land Q \land R$

4. For $(P = F, Q = F, R = T)$:
   $\neg P \land \neg Q \land R$

**PDNF:**
$(P \land Q \land R) \lor (P \land Q \land \neg R) \lor (\neg P \land Q \land R) \lor (\neg P \land \neg Q \land R)$

### 3. Principal Conjunctive Normal Form (PCNF)

The PCNF is a conjunction (AND) of all the maxterms where the formula $F$ is false.

From the truth table, $F$ is false for:

- Row 3: $(P = T, Q = F, R = T)$
- Row 4: $(P = T, Q = F, R = F)$
- Row 6: $(P = F, Q = T, R = F)$
- Row 8: $(P = F, Q = F, R = F)$

**Maxterms where the formula is false:**

1. For $(P = T, Q = F, R = T)$:
   $\neg P \lor Q \lor \neg R$

2. For $(P = T, Q = F, R = F)$:
   $\neg P \lor Q \lor R$

3. For $(P = F, Q = T, R = F)$:
   $P \lor \neg Q \lor R$

4. For $(P = F, Q = F, R = F)$:
   $P \lor \neg Q \lor \neg R$

**PCNF:**
$(\neg P \lor Q \lor \neg R) \land (\neg P \lor Q \lor R) \land (P \lor \neg Q \lor R) \land (P \lor \neg Q \lor \neg R)$

### Summary

- **PDNF:** $(P \land Q \land R) \lor (P \land Q \land \neg R) \lor (\neg P \land Q \land R) \lor (\neg P \land \neg Q \land R)$
- **PCNF:** $(\neg P \lor Q \lor \neg R) \land (\neg P \lor Q \lor R) \land (P \lor \neg Q \lor R) \land (P \lor \neg Q \lor \neg R)$

# 5. To show that the formula

$\forall x \, (P(x) \rightarrow Q(x)) \land \forall x \, (Q(x) \rightarrow R(x)) \rightarrow \forall x \, (P(x) \rightarrow R(x))$

is valid, we'll use logical reasoning and rules of inference.

### Logical Reasoning

We need to show that if:

1. $\forall x \, (P(x) \rightarrow Q(x))$ is true.
2. $\forall x \, (Q(x) \rightarrow R(x))$ is true.

Then it must follow that:

3. $\forall x \, (P(x) \rightarrow R(x))$ is also true.

**Proof:**

1. **Assumption 1: $\forall x \, (P(x) \rightarrow Q(x))$**

   This means that for every element $x$ in the domain, if $P(x)$ is true, then $Q(x)$ must be true.

2. **Assumption 2: $\forall x \, (Q(x) \rightarrow R(x))$**

   This means that for every element $x$ in the domain, if $Q(x)$ is true, then $R(x)$ must be true.

3. **To Prove: $\forall x \, (P(x) \rightarrow R(x))$**

   We need to show that for every element $x$ in the domain, if $P(x)$ is true, then $R(x)$ must be true.

   **Proof Steps:**

   - Consider an arbitrary element $x$ in the domain.
   - Suppose $P(x)$ is true.
   
     According to Assumption 1: $P(x) \rightarrow Q(x)$.

     Since $P(x)$ is true, $Q(x)$ must also be true (by Modus Ponens).

   - Now, with $Q(x)$ being true, apply Assumption 2: $Q(x) \rightarrow R(x)$.

     Since $Q(x)$ is true, $R(x)$ must also be true (by Modus Ponens).

   - Therefore, if $P(x)$ is true, then $R(x)$ must be true.

   - This reasoning holds for any arbitrary $x$ in the domain.

   Hence, $\forall x \, (P(x) \rightarrow R(x))$ is true.


$\forall x \, (P(x) \rightarrow Q(x)) \land \forall x \, (Q(x) \rightarrow R(x)) \rightarrow \forall x \, (P(x) \rightarrow R(x))$
is valid.