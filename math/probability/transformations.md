Transformation of Random Variables
==================================
# Transformations on Continuous Random Variables
* Given the density function of $X$ how can we find the density function of $Y$?
  1. Find CDF of $Y$ using CDF of $X$.
  2. Take the derivative of the CDF to get the density.
* Let $Y = g(X)$. Suppose that the inverse of $g$ exists and is strictly monotonically increasing ($g'(x) > 0$).

$$
\begin{align*}
P_Y(y) &= P(g(X) \le y) = P(X \le g^{-1}(y)) \\
  &= P_X(g^{-1}(y))
\end{align*}
$$

* Taking the derivative of both sides give:

$$
\begin{align*}
p_Y(y) &= p_X(g^{-1}(y)) \frac{g^{-1}(y)}{dy}
\end{align*}
$$

* Suppose instead that $g$ is monotonically decreasing $g'(x) < 0$.

$$
\begin{align*}
P_Y(y) &= P(g(X) \le y) = P(X \ge g^{-1}(y)) \\
  &= 1 - P_X(g^{-1}(y))
\end{align*}
$$

* Taking the derivative of both sides becomes

$$
\begin{align*}
p_Y(y) &= p_X(g^{-1}(y)) \left(-\frac{g^{-1}(y)}{dy}\right)
\end{align*}
$$

* Combining both cases we get:

$$
\begin{align*}
p_Y(y) = p_X(g^{-1}(y)) \left|\frac{g^{-1}(y)}{dy}\right|
\end{align*}
$$

# Inverse Sampling Transformation
* What is the ditribution of $Y = P_X(X)$? Note $P_X$ is always monotonically increasing.

$$
\begin{align*}
P_Y(y) = P(P_X(X) \le y) = P(X \le P_X^{-1}(y)) = P_X(P_X^{-1}(y)) = y 
\end{align*}
$$

* If $P_Y(y) = y$, then that indicates that $Y$ is a uniform random variable $U$ in $[0, 1]$.
* Thus we have that $X = P_X^{-1}(U)$.
* To generate samples of random variable $X$ with known distribution $P_X$ we must
  1. Generate samples from uniform distribution in $[0, 1]$
  2. Applying $P_X$ to the generated samples.   

# Multivariate Transformations
* Suppose $Y = g(X)$ where $g$ has an inverse.
* In the multivariate case, we get the following density relationship (note $J_{g^{-1}}$ is the Jacobian of $g^{-1}$):

$$
\begin{align*}
p_Y(y) = p_X(x) |J_{g^{-1}}|
\end{align*}
$$

