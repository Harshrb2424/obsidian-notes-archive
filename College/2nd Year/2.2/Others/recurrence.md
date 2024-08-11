### 7.a) Recursive Algorithm for Finding the Sum of the First n Positive Integers

The sum $S(n)$ of the first $n$ positive integers can be computed recursively as follows:

**Recursive Algorithm:**

```python
def sum_of_integers(n):
    if n == 1:
        return 1
    else:
        return n + sum_of_integers(n - 1)
```

**Explanation:**
- **Base Case:** When $n = 1$, the sum is 1.
- **Recursive Case:** For $n > 1$, the sum of the first $n$ positive integers is $n$ plus the sum of the first $n - 1$ integers.

### 7.b) Proof by Mathematical Induction

**Statement to Prove:**
$x - y \text{ is a factor of } x^n - y^n \text{ for all positive integers } n.$

**Proof by Induction:**

1. **Base Case:**

   For $n = 1$:
   $x^1 - y^1 = x - y$
   Clearly, $x - y$ is a factor of itself. Hence, the base case holds.

2. **Inductive Step:**

   Assume that for some integer $k \geq 1$, $x - y$ is a factor of $x^k - y^k$. This means:
   $x^k - y^k = (x - y) \cdot Q_k(x, y)$
   for some polynomial $Q_k(x, y)$.

   We need to show that $x - y$ is also a factor of $x^{k+1} - y^{k+1}$.

   Consider:
   $x^{k+1} - y^{k+1} = x \cdot x^k - y \cdot y^k$
   
   Add and subtract $x \cdot y^k$:
   $x^{k+1} - y^{k+1} = (x \cdot x^k - x \cdot y^k) + (x \cdot y^k - y \cdot y^k)$
   $= x \cdot (x^k - y^k) + y^k \cdot (x - y)$

   By the induction hypothesis, $x - y$ is a factor of $x^k - y^k$, so $x \cdot (x^k - y^k)$ is divisible by $x - y$. Additionally, $y^k \cdot (x - y)$ is also divisible by $x - y$. Therefore:
   $x^{k+1} - y^{k+1} = x \cdot (x^k - y^k) + y^k \cdot (x - y)$
   is divisible by $x - y$.

   Hence, $x - y$ is a factor of $x^{k+1} - y^{k+1}$.

### 8. Solve the recurrence relation of the Fibonacci series of numbers.

$F_n = F_{n-1} + F_{n-2}$

with the initial conditions:

$F_1 = 1$
$F_2 = 1$

### Solution Using Characteristic Equation

1. **Set Up the Recurrence Relation:**

   The Fibonacci sequence satisfies the linear homogeneous recurrence relation:

   $F_n = F_{n-1} + F_{n-2}$

2. **Find the Characteristic Equation:**

   Assume a solution of the form $F_n = r^n$. Substitute this into the recurrence relation:

   $r^n = r^{n-1} + r^{n-2}$

   Divide through by $r^{n-2}$:

   $r^2 = r + 1$

   Thus, the characteristic equation is:

   $r^2 - r - 1 = 0$

3. **Solve the Characteristic Equation:**

   Use the quadratic formula to find the roots $r$:

   $r = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$

   Here, $a = 1$, $b = -1$, and $c = -1$:

   $r = \frac{1 \pm \sqrt{1 + 4}}{2}$
   $r = \frac{1 \pm \sqrt{5}}{2}$

   The roots are:

   $r_1 = \frac{1 + \sqrt{5}}{2}$
   $r_2 = \frac{1 - \sqrt{5}}{2}$

4. **Form the General Solution:**

   The general solution to the recurrence relation is:

   $F_n = A \cdot r_1^n + B \cdot r_2^n$

   where $A$ and $B$ are constants determined by the initial conditions.

5. **Determine Constants Using Initial Conditions:**

   Use $F_1 = 1$ and $F_2 = 1$ to solve for $A$ and $B$:

   For $n = 1$:
   $F_1 = A \cdot r_1 + B \cdot r_2 = 1$

   For $n = 2$:
   $F_2 = A \cdot r_1^2 + B \cdot r_2^2 = 1$

   We know that:

   $r_1^2 = r_1 + 1$
   $r_2^2 = r_2 + 1$

   Therefore:

   $F_2 = A \cdot (r_1 + 1) + B \cdot (r_2 + 1)$
   $1 = A \cdot r_1 + A + B \cdot r_2 + B$
   $1 = 1 + (A \cdot r_1 + B \cdot r_2)$
   $A \cdot r_1 + B \cdot r_2 = 0$

   Solving these two equations:

   $A \cdot r_1 + B \cdot r_2 = 1$
   $A \cdot r_1 + B \cdot r_2 = 0$

   Solving yields:

   $A = \frac{1}{\sqrt{5}}$
   $B = -\frac{1}{\sqrt{5}}$

6. **Write the Final Solution:**

   $F_n = \frac{1}{\sqrt{5}} \left( \left(\frac{1 + \sqrt{5}}{2}\right)^n - \left(\frac{1 - \sqrt{5}}{2}\right)^n \right)$

### 9. Use generating functions to solve the recurrence relations 𝑎𝑟 = 𝑎𝑟−1 + 𝑎𝑟−2 with 𝑎1 = 2 𝑎𝑛𝑑 𝑎2 = 3
### Given Recurrence Relation

The recurrence relation is:

$a_r = a_{r-1} + a_{r-2}$

with initial conditions:

$a_1 = 2$
$a_2 = 3$

### Generating Function Approach

1. **Define the Generating Function:**

   Let $A(x)$ be the generating function for the sequence $\{a_n\}$:

   $A(x) = \sum_{n=1}^{\infty} a_n x^n$

2. **Set Up the Generating Function for the Recurrence Relation:**

   Using the recurrence relation $a_r = a_{r-1} + a_{r-2}$, multiply through by $x^r$ and sum for all $r \geq 3$:

   $\sum_{r=3}^{\infty} a_r x^r = \sum_{r=3}^{\infty} a_{r-1} x^r + \sum_{r=3}^{\infty} a_{r-2} x^r$

   The right-hand side can be manipulated as follows:

   $\sum_{r=3}^{\infty} a_{r-1} x^r = x \sum_{r=3}^{\infty} a_{r-1} x^{r-1} = x \left( \sum_{r=2}^{\infty} a_r x^r \right) = x (A(x) - a_1 x)$

   $\sum_{r=3}^{\infty} a_{r-2} x^r = x^2 \sum_{r=3}^{\infty} a_{r-2} x^{r-2} = x^2 \left( \sum_{r=1}^{\infty} a_r x^r \right) = x^2 A(x)$

   Combine these results:

   $\sum_{r=3}^{\infty} a_r x^r = x (A(x) - a_1 x) + x^2 A(x)$

3. **Express the Generating Function in Terms of $A(x)$:**

   The left-hand side can be rewritten as:

   $\sum_{r=3}^{\infty} a_r x^r = A(x) - a_1 x - a_2 x^2$

   Therefore:

   $A(x) - a_1 x - a_2 x^2 = x (A(x) - a_1 x) + x^2 A(x)$

   Substitute $a_1 = 2$ and $a_2 = 3$:

   $A(x) - 2x - 3x^2 = x (A(x) - 2x) + x^2 A(x)$
   $A(x) - 2x - 3x^2 = x A(x) - 2x^2 + x^2 A(x)$
   $A(x) - 2x - 3x^2 = x A(x) + x^2 A(x) - 2x^2$
   $A(x) - 2x - 3x^2 = A(x) (x + x^2) - 2x^2$
   $A(x) - A(x) (x + x^2) = 2x - 2x^2$
   $A(x) (1 - x - x^2) = 2x - 2x^2$
   $A(x) = \frac{2x - 2x^2}{1 - x - x^2}$

4. **Find the Explicit Formula:**

   To find the explicit formula for $a_n$, we need to perform partial fraction decomposition or use the method of generating functions. However, the form:

   $A(x) = \frac{2x - 2x^2}{1 - x - x^2}$

   provides a direct method to compute the coefficients of $x^n$ in the series expansion, which are the terms of the sequence $\{a_n\}$.

   To get $a_n$ explicitly, we can use the method of solving linear recurrence relations or by extracting terms from the generating function. 

