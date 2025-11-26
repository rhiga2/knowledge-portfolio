Latent Variable Models
=====================
# The EM Algorithm
* Log likelihood $\log p_\theta(x)$ may not have a closed form gradient.
* Introduce latent variable $z$. Joint log-likelihood has a closed form gradient $\log p_\theta(x, z)$.
  * In mixture models, $z$ is the assignment of $x$ to a distribution.
* Evidence Lower Bound: Suppose the latent variables are derived from some distribution $q$

$$
\begin{align*}
l(\theta) &= \log p_\theta(x) = E_{z \sim q} \log p_\theta(x) \\ 
&= E_{z \sim q} \log \frac{p_\theta(x, z)} {p_\theta(z|x)} \\
&= E_{z \sim q} \log \left( \frac{p_\theta(x, z)} {p_\theta(z|x)} \frac{q(z)}{q(z)}\right) \\
&= \underbrace{E_{z \sim q} \log \frac{p_\theta(x, z)}{q(z)}}_{L(q, \theta)} + \underbrace{E_{z \sim q} \log \frac{q(z)}{p_\theta(z | x)}}_{D_{KL}(q \parallel p_\theta(\cdot | x))}
\end{align*}
$$

* Since KL divergence is always positive, we know that $L(q, \theta)$ is a lower bound to the log-likelihood.
* The EM algorithm will alternate between tightening the lower bound (E-step) and maximizing the lower bound (M-step). The intuition is that increasing a tight lower bound will maximize the likelihood.   
