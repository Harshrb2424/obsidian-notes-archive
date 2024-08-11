Certainly! Here are the formulas for the requested topics in markdown format compatible with Obsidian:

### Linear Regression

**Linear Regression:**

The linear regression equation is given by: $y = ax + b$

Where:
- $y$ is the dependent variable,
- $x$ is the independent variable,
- $a$ is the slope (coefficient),
- $b$ is the y-intercept.

### Least Squares and the Fitted Model: Method of Least Squares

**Method of Least Squares:**
Minimizing the sum of squared differences between observed (\( y_i \)) and predicted $(\( \hat{y}_i \))$ values.

## **Fitting a Straight Line: 
$y = ax + b$**

Normal Equations:

$\sum y = an + b \sum x$

$\sum xy = a \sum x + b \sum x^2$

Where:
- $y$ is the dependent variable,
- $x$ is the independent variable,
- $\sum y$ is the sum of the dependent variable,
- $\sum x$ is the sum of the independent variable,
- $\sum xy$ is the sum of the product of x and y,
- $a$ is the slope (coefficient),
- $b$ is the y-intercept.

## **Fitting a Parabola (2nd Degree):**
$y = a + bx + cx^2$

Normal Equations:

$\sum y = an + b\sum x + c\sum x^2$

$\sum xy = a\sum x + b\sum x^2 + c\sum x^3$

$\sum x^2y = a\sum x^2 + b\sum x^3 + c\sum x^4$

Where:
- $y$ is the dependent variable,
- $x$ is the independent variable,
- $\sum y$ is the sum of the dependent variable,
- $\sum x$ is the sum of the independent variable,
- $\sum x^2$ is the sum of the squared independent variable,
- $\sum xy$ is the sum of the product of x and y,
- $\sum x^2y$ is the sum of the product of $x^2$ and y,
- $a$, $b$, and $c$ are coefficients.


**Exp Curve: Formula, Normal Equations:**
Exponential Curve:
$y = ae^{bx}$

Taking the natural logarithm of both sides:
$\ln(y) = \ln(ae^{bx})$

Simplifying using logarithmic properties:
$\ln(y) = \ln(a) + \ln(e^{bx})$

Since $\ln(e^x) = x$:
$\ln(y) = \ln(a) + bx$

Let $Y = \ln(y)$ and $A = \ln(a)$, then:
$Y = A + bx$

Normal Equations:

$\sum Y = nA + b\sum x$

$\sum xY = A\sum x + b\sum x^2$

By solving these equations, we can obtain the values of $A$ and $b$. 
With $A = \ln(a)$, we can find $a$ by taking the exponential of $A$:
$a = e^A$


**Power Curve: Formula, Normal Equations:**
Exponential Curve: $y = ab^x$

Taking the base-10 logarithm of both sides:
$\log_{10}(y) = \log_{10}(ab^x)$

Simplifying using logarithmic properties:
$\log_{10}(y) = \log_{10}(a) + \log_{10}(b^x)$

Since $\log_{10}(b^x) = x \log_{10}(b)$:
$\log_{10}(y) = \log_{10}(a) + x \log_{10}(b)$

Let $Y = \log_{10}(y)$, $A = \log_{10}(a)$, and $B = \log_{10}(b)$, then:
$Y = A + Bx$

Normal Equations:

$\sum Y = nA + B\sum x$

$\sum xY = A\sum x + B\sum x^2$

By solving these equations, we can obtain the values of $A$ and $B$. 
With $A = \log_{10}(a)$, we can find $a$ by taking the power of 10 of $A$:
$a = 10^A$

Similarly, with $B = \log_{10}(b)$, we can find $b$ by taking the power of 10 of $B$:
$b = 10^B$

### Karl Pearson's Coefficient of Correlation:

The coefficient of correlation ($r$) between variables $X$ and $Y$ is calculated using the formula:

$r = \frac{\sum xy}{\sqrt{\sum x^2 \sum y^2}}$

Where:
- $\sum xy$ is the sum of the product of $X$ and $Y$,
- $\sum x^2$ is the sum of the squares of $X$,
- $\sum y^2$ is the sum of the squares of $Y$.

### Mean of Values

Mean of $X$ values ($\bar{x}$):
$\bar{x} = \frac{\sum x_i}{n}$

Mean of $Y$ values ($\bar{y}$):
$\bar{y} = \frac{\sum y_i}{n}$

### Deviations from the Mean

Deviations from the mean are calculated as:
$X = x - \bar{x}$
$Y = y - \bar{y}$
### Properties of Coefficient of Correlation

1. **Range of \( r \):**
   - The coefficient of correlation ($r$) always lies between -1 and 1, inclusive: $-1 \leq r \leq 1$.

2. **Direction of \( r \):**
   - If $r > 0$, there is a positive correlation (direct relationship).
   - If $r < 0$, there is a negative correlation (inverse relationship).
   - If $r = 0$, there is no linear correlation.

3. **Magnitude of \( r \):**
   - The closer $r$ is to -1 or 1, the stronger the linear correlation.
   - The closer $r$ is to 0, the weaker the linear correlation.

### Coefficient of Correlation
Mean of $X$ values ($\bar{x}$):
$\bar{x} = \frac{\sum x_i}{n}$

Mean of $Y$ values ($\bar{y}$):
$\bar{y} = \frac{\sum y_i}{n}$

For all terms
$X = x - \bar{x}$
$Y = y - \bar{y}$

Equation of regression line y on x:
$y - \bar{y} = \frac{\sum{XY}}{\sum{X^2}} \cdot (x - \bar{x})$
Equation of regression line x on y:
$x - \bar{x} = \frac{\sum{XY}}{\sum{Y^2}} \cdot (y - \bar{y})$

