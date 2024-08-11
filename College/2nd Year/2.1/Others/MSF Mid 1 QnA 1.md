# **1) What is the fermat number? find the factor of 809009 by using fermat method of factorization.**
![[Pasted image 20231124220101.png]]

![[Pasted image 20231124220140.png]]
# **2) Solve the system of linear eq wing chinese remainder theorems x=2(mod3), x=3 (mod 5), x=2(mod 7)**
![[Pasted image 20231124220254.png]]
![[Pasted image 20231124220304.png]]
# **3) Fit a straight line y=ax+b for the following data**
   
|   x   |   0   |   1   |   2   |   3   |   4   |
|-------|-------|-------|-------|-------|-------|
| F(x)  |   1   |   1.8 |   3.3 |   4.5 |   6.3 |


The normal equations provide an alternative method for finding the coefficients $(a)$ and $(b)$ in the equation $(y = ax + b)$ for the least squares regression line. The normal equations are given by:

$\sum y = a \sum x + nb$

$\sum xy = a \sum x^2 + b \sum x$

 values using the provided data:

$n = 5$

$\Sigma x = 0 + 1 + 2 + 3 + 4 = 10$

$\Sigma y = 1 + 1.8 + 3.3 + 4.5 + 6.3 = 16$

$\Sigma xy = (0 \cdot 1) + (1 \cdot 1.8) + (2 \cdot 3.3) + (3 \cdot 4.5) + (4 \cdot 6.3) = 44.1$

$\Sigma x^2 = (0^2) + (1^2) + (2^2) + (3^2) + (4^2) = 30$


Substitute these values into the normal equations:

$16 = a \cdot 10 + 5b$
$44.1 = a \cdot 30 + 10b$

Let's solve it step by step:

Equation 1: $16 = 10a + 5b$
Equation 2: $44.1 = 30a + 10b$

Multiply Equation 1 by 2 to make the coefficients of $b$ match:
$32 = 20a + 10b$

Now, subtract Equation 2 from the modified Equation 1:
$32 - 44.1 = (20a + 10b) - (30a + 10b)$

Solve for $a$:
$-12.1 = -10a$
$a = 1.21$

Now substitute the value of $a$ back into Equation 1 to solve for $b$:

$16 = 10(1.21) + 5b$
$16 = 12.1 + 5b$
$5b = 3.9$
$b = 0.78$

So, the values of $a$ and $b$ are $1.21$ and $0.78$ respectively. Therefore, the equation of the least squares regression line is $(y = 1.21x + 0.78)$.

# **4) A play on tosses 3 fair coins. He wins Rs.500 of three heads, Rs 300 of two heads appear, Rs.100 if one head occurs. on the other hand He loses Rs.1500 if 3 tails occurs. find the expected gain of player.**
![[Pasted image 20231125203940.png]]

# **5) find mean and variance of the uniform probability distribution given by f(x) = 1/n for x=1,2,3,...n**

For a uniform probability distribution given by $f(x) = \frac{1}{n}$ for $x = 1, 2, 3, \ldots, n$, the mean ($\mu$) and variance ($\sigma^2$) can be calculated as follows:

1. **Mean ($\mu$):**
   The mean is the average value and is given by the formula:
   $\mu = \sum_{i=1}^{n} x_i \cdot P(x_i)$
   where $x_i$ are the possible values of $x$ (in this case, 1 to $n$) and $P(x_i)$ is the corresponding probability.

   For this uniform distribution, $P(x_i) = \frac{1}{n}$ for all $x_i$. Therefore, the mean is the sum of all possible values divided by $n$:
   $\mu = \frac{1}{n} \sum_{i=1}^{n} x_i$

   For the given distribution:
   $\mu = \frac{1}{n} \sum_{i=1}^{n} i$
   $\mu = \frac{1}{n} \sum_{i=1}^{n} i$
   $\mu = \frac{1}{n} \cdot \frac{n \cdot (n + 1)}{2}$
   $\mu = \frac{n + 1}{2}$

2. **Variance ($\sigma^2$):**
   The variance is a measure of the spread of the distribution and is given by:
   $\sigma^2 = \sum_{i=1}^{n} (x_i - \mu)^2 \cdot P(x_i)$
   where $\mu$ is the mean.

   For this uniform distribution, $P(x_i) = \frac{1}{n}$ for all $x_i$. Therefore, the variance is:
![[Pasted image 20231126110817.png]]![[Pasted image 20231126110826.png]]
Therefore, the mean $\mu$ is $\frac{n + 1}{2}$ and the variance $\sigma^2$ is $\frac{n^2 -1}{12}$ for the given uniform probability distribution.
# **6) A sample of 4 items is selected at random from a box containing 12 items of which 5 are defective. Find the expected number 'E' of defective items.**

![[Pasted image 20231125204114.png]]![[Pasted image 20231125204130.png]]
# **7) What is the fermat number? find the factor of 426749 by using formal method of factorization.**
![[Pasted image 20231124220101.png]]

### factor of 426749 by using formal method of factorization:
1. **Choose $t$:**
   Let's choose $t = 655$ (you can experiment with different values).

2. **Check $t^2 - N$:**
	Calculate $t^2 - N$ and check if it's a perfect square. If $t^2 - N = s^2$ for some $s$, then $N$ can be factored as $(t + s)(t - s)$.
   $656^2 - 426749 = 430336 - 426749 = 3587$
   Since 3587 is not a perfect square, we need to choose a different value for $t$ and repeat the process.

3. **Choose a Different $t$:**
   Let's try another value. Let's choose $t = 657$.

4. **Check $t^2 - N$:**
   $657^2 - 426749 = 431649 - 426749 = 4900$
   Now, $t^2 - N = 4900$, which is a perfect square ($70^2$).

5. **Factorize Using the Result:**
   Since $s^2 = t^2 - N = 4900$ and $4900 = 70^2$, we can write $N$ as the difference of two squares:
   $N = t^2 - s^2 = (t + 70)(t - 70)$
   Therefore, the factors of 426749 are $t + 70$ and $t - 70$.

6. **Calculate Factors:**
   $a + 70 = 657 + 70 = 727$
   $a - 70 = 657 - 70 = 587$

**Therefore, the factors of 426749 are 587 and 727.** 

# **8) solve the system of linear equation using chinese remainder theorem x=5 (mod 6), 1 = 4 (mod 11) x = 3 (mod17)**
![[WhatsApp Image 2023-11-26 at 11.23.44_cb70b2f4.jpg]]
![[WhatsApp Image 2023-11-26 at 11.23.44_e06cd93a.jpg]]
![[WhatsApp Image 2023-11-26 at 11.23.45_bde4c6ff.jpg]]
# **9) Out of 800 families with 5 children each how would many you expect to have a) 3 boys b)5 girls c) either 2 (or) 3 boys d) atleast one boy? Assume equal properties probabilities for boys and girls.**
![[Pasted image 20231125204329.png]]
![[Pasted image 20231125204342.png]]![[Pasted image 20231125204351.png]]![[Pasted image 20231125204400.png]]
# **10) Write the proof mean of normal distribution.**
![[WhatsApp Image 2023-11-26 at 11.23.45_d1355a18.jpg]]
![[WhatsApp Image 2023-11-26 at 11.23.45_3e019012.jpg]]
# **11) Write proof variance of normal distribution** 
![[WhatsApp Image 2023-11-26 at 11.23.46_fb9bded0.jpg]]
![[WhatsApp Image 2023-11-26 at 11.23.46_17f11923.jpg]]
# **calculate expectation and variance of 'X' variance of the probability distribution of the random variable 'X' is given by**

|   x   |   -1  |   0   |   1   |   2   |   3   |
|-------|-------|-------|-------|-------|-------|
| F(x)  |  0.3  |  0.1  |  0.1  |  0.3  |  0.2  |

Given the probability distribution of $X$:

|   x   |   -1  |   0   |   1   |   2   |   3   |
|-------|-------|-------|-------|-------|-------|
| F(x)  |  0.3  |  0.1  |  0.1  |  0.3  |  0.2  |
1. Expectation ($\mu$):
$\mu = E(X) = \sum_{i} x_i \cdot P(X = x_i)$
$\mu = (-1 \cdot 0.3) + (0 \cdot 0.1) + (1 \cdot 0.1) + (2 \cdot 0.3) + (3 \cdot 0.2)$
$\mu = -0.3 + 0 + 0.1 + 0.6 + 0.6$
$\mu = 1$

2. Variance ($\sigma^2$):
$\sigma^2 = \sum_{i} x_i^2 \cdot P(X = x_i) - \mu^2$

Given that $\mu = 1$ (calculated previously), let's use this formula to find the variance:

$\sigma^2 = \sum_{i} x_i^2 \cdot P(X = x_i) - \mu^2$
$\sigma^2 = (-1)^2 \cdot 0.3 + (0)^2 \cdot 0.1 + (1)^2 \cdot 0.1 + (2)^2 \cdot 0.3 + (3)^2 \cdot 0.2 - 1^2$
$\sigma^2 = 0.3 + 0 + 0.1 + 1.8 + 1.2 - 1$
$\sigma^2 = 2.4$

So, the expectation ($\mu$) is 1, and the variance ($\sigma^2$) is 2.4 for the given probability distribution.
# **12) A sample of u items is selected a vandom from a box containing 12 items of which 5 are defective. Find the expected number 'E' of defective items**
### // Same Question 6
# **13) In normal distribution define define mean = median = mode**
### // Not given