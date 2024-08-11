# B.Tech 2nd Year - Mathematical and Statistical Foundations (MSF)
## UNIT I: Number Theory

### Greatest Common Divisors and Prime Factorization

#### Greatest Common Divisors (GCD)

The GCD of integers *a (greater number)* and *b* is denoted as $$\text{GCD}(a, b)$$

#### Euclidean Algorithm:
$$\text{GCD}(a, b) = \text{GCD}(b, a \mod b)$$
where *\mod* denotes the remainder when *a* is divided by *b*.


$a = bq + r, \quad 0 \leq r < b$
$b = rq_1 + r_1, \quad 0 \leq r_1 < r$
$r = r_1q_1 + r_2, \quad 0 \leq r_2 < r_1$
...
$r_{i-2}  = r_{i-1} q_{i} + r_i$
$r_{i-1} = r_i q_{i+1} + 0$
(keep dividing until 0 comes)
#### The Fermat Numbers

Fermat numbers are given by the formula:
$$F_n = 2^{2^n} + 1$$
where *n* is a non-negative integer.

1. $n = 0$: $2^{2^0} + 1 = 2^1 + 1 = 3$
2. $n = 1$: $2^{2^1} + 1 = 2^2 + 1 = 5$
3. $n = 2$: $2^{2^2} + 1 = 2^4 + 1 = 17$
4. $n = 3$: $2^{2^3} + 1 = 2^8 + 1 = 257$
5. $n = 4$: $2^{2^4} + 1 = 2^{16} + 1$


#### Format's Method of Factorization

Starting with the given equation:
$n = ab = \left(\frac{a+b}{2}\right)^2 - \left(\frac{a-b}{2}\right)^2$
$n = ab = t^2 - s^2$

Now, let's express \(a\) and \(b\) in terms of \(t\) and \(s\):

$\frac{a+b}{2} = t$
$a + b = 2t$
$a = 2t - b$

Similarly,
$\frac{a-b}{2} = s$
$a - b = 2s$
$b = 2t - a$

Now, substitute these expressions for \(a\) and \(b\) back into the original equation:

$n = ab = (2t - b)b = t^2 - s^2$

$t = \sqrt{n} + 1$