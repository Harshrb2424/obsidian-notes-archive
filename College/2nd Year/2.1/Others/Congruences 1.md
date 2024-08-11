# B.Tech 2nd Year - Mathematical and Statistical Foundations (MSF)
## UNIT II: Congruences

### Congruences

#### Introduction to Congruences

**Definition:**
A congruence is a relation between integers that have the same remainder when divided by a given positive integer called the modulus.

**Notation:**
If $a$, $b$, and $m$ are integers with $m > 0$, we say that $a$ is congruent to $b$ modulo $m$ and write $$a \equiv b \pmod{m}$$ if $m$ divides $a - b$.

#### Linear Congruences

**Definition:**
A linear congruence is an equation of the form $$ax \equiv b \pmod{m}$$where $a$, $b$, and $m$ are integers, and $m > 0$.

**Solution:**
A linear congruence $ax \equiv b \pmod{m}$ has a solution if and only if $d$ divides $b$, where $d = \gcd(a, m)$.

#### The Chinese Remainder Theorem

**Theorem:**
Let $m_1, m_2, \ldots, m_k$ be positive integers that are pairwise coprime (i.e., $\gcd(m_i, m_j) = 1$ for all $i \neq j$). For any integers $a_1, a_2, \ldots, a_k$, the system of simultaneous congruences:
$$\[ \begin{align*} x &\equiv a_1 \pmod{m_1} \\ x &\equiv a_2 \pmod{m_2} \\ & \vdots \\ x &\equiv a_k \pmod{m_k} \end{align*} \]$$
has a unique solution  $modlo M = m_1 \cdot m_2 \cdot \ldots \cdot m_k$.

#### Systems of Linear Congruences

**System of Equations:**
A system of linear congruences is a set of equations of the form:
$$\[ \begin{align*} a_{11}x_1 &\equiv b_1 \pmod{m_1} \\ a_{21}x_2 &\equiv b_2 \pmod{m_2} \\ & \vdots \\ a_{k1}x_k &\equiv b_k \pmod{m_k} \end{align*} \]$$
where $a_{ij}$, $b_i$, and $m_i$ are integers.
A system of linear congruences has a unique solution if and only if the modulus values are pairwise coprime. In other words, for a system of linear congruences:
**Solution:**
A solution to the system exists if and only if each pair of congruences in the system is consistent.

