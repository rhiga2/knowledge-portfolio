Transformation of Random Variables
==================================
# Transformations on Continuous Random Variables
* Given the density function of $X$ how can we find the density function of $Y$?
  1. Find CDF of $Y$ using CDF of $X$.
  2. Take the derivative of the CDF to get the density.
* Let $Y = g(X)$. Suppose that the inverse of $g$ exists and is strictly monotonically increasing ($g'(x) > 0$).

$$
\begin{align*}
F_Y(y) &= P(g(X) \le y) = P(X \le g^{-1}(y)) \\
  &= F_X(g^{-1}(y))
\end{align*}
$$

* Taking the derivative of both sides give:

$$
\begin{align*}
f_Y(y) &= f_X(g^{-1}(y)) \frac{g^{-1}(y)}{dy}
\end{align*}
$$

* Suppose instead that $g$ is monotonically decreasing $g'(x) < 0$.

$$
\begin{align*}
F_Y(y) &= P(g(X) \le y) = P(X \ge g^{-1}(y)) \\
  &= 1 - F_X(g^{-1}(y))
\end{align*}
$$

* Taking the derivative of both sides becomes

$$
\begin{align*}
f_Y(y) &= f_X(g^{-1}(y)) \left(-\frac{g^{-1}(y)}{dy}\right)
\end{align*}
$$

* Combining both cases we get:

$$
\begin{align*}
f_Y(y) = f_X(g^{-1}(y)) \left|\frac{g^{-1}(y)}{dy}\right|
\end{align*}
$$

# Inverse Sampling Transformation
* What is the ditribution of $Y = F_X(X)$? Note $F_X$ is always monotonically increasing.

$$
\begin{align*}
F_Y(y) = P(F_X(X) \le y) = P(X \le F_X^{-1}(y)) =
F_X(F_X^{-1}(y)) = y 
\end{align*}
$$

* If $F_Y(y) = y$, then that indicates that $Y$ is a uniform random variable $U$ in $[0, 1]$.
* Thus we have that $X = F_X^{-1}(U)$.
* To generate samples of random variable $X$ with known distribution $F_X$ we must
  1. Generate samples from uniform distribution in $[0, 1]$
  2. Applying $F_X$ to the generated samples.   

# Multivariate Transformations
* Suppose $Y = g(X)$ where $g$ has an inverse.
* In the multivariate case, we get the following density relationship (note $J_{g^{-1}}$ is the Jacobian of $g^{-1}$):

$$
\begin{align*}
f_Y(y) = f_X(x) |J_{g^{-1}}|
\end{align*}
$$

