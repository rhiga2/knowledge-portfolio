Classifcation
=======================

# Discriminant Analysis
## Quadratic Discriminant Analysis
* Assume $x | y=k \sim N(\mu_k, \Sigma_k)$ and that $p(y=k) = \pi_k$
* By Bayes Rule, we have:

$$
p(y = k | x) \propto p(x | y = k) * p(y = k) = \pi_k N(x | \mu_k, \Sigma_k) 
$$

* Inference Rule:

$$
\max_k \log p(y = k | x) = \underbrace{\log \pi_k + \log N(x | \mu_k, \Sigma_k)}_{d_k(x)}
$$

* $d_k(x)$ is called discriminant

$$
d_k(x) = \log \pi_k - \frac{1}{2} (x - \mu_k)^T \Sigma_k^{-1} (x - \mu) - \frac{1}{2} \log | \Sigma_k |
$$

* TODO: Training

## Linear Discriminant Analysis
* Instead of assuming that we have a different covariance matrix for each class we assume that all class distributions share a global covariance matrix $\Sigma$
* Discriminant becomes linear if we eliminate terms that do not depend on $k$:

$$
d_k(x) \equiv \log \pi_k - \frac{1}{2} (x - \mu_k)^T \Sigma^{-1} (x - \mu_k) \equiv \log \pi_k - \frac{1}{2} (-2 x^T \Sigma^{-1} \mu_k + \mu_k^T \Sigma^{-1} \mu_k^T)
$$

# Naive Bayes
* Naive Bayes are a set of models that assume that all features of $x_j$ are conditional independent given $y$ (Naive Bayes Assumption). 
* We can simplify discriminants as:

$$
d_k(x) = \log p(y = k | x) = \log p(y = k) + \log p(x | y = k) = \log p(y = k) + \sum_{j=1}^d \log p(x_j | y = k)
$$

## Example: Naive Bayes QDA
* Under the Naive Bayes assumption, the covariance matrix is diagonal $\Sigma_k = \text{diag}(\sigma_k)$. 

$$
d_k(x) = \log \pi_k - \frac{1}{2} \sum_{j=1}^d \frac{(x_j - \mu_{kj})^2}{\sigma_{kj}^2}
$$

* With QDA we have to estimate $Kd^2$ covarances. 
* Naive Bayes reduces param count of varainces to just $Kd$  

# Logistic and Softmax Regression
## Logistic Regression
* Binary classification technique. We assume that $y$ is either $0$ pr $1$
* Assume that $y | x$ is a Bernoulli distribution parameterized by $g(w^Tx)$.
  * $g$ is often a sigmoid function since it maps between $[0, 1]$
  * $w$ are the parameters of our model.

* The sigmoid function is given by:

$$
g(z) =  \frac{1}{1+e^{-z}}
$$

* We can maximize the likelihood  as: 

$$
p(y | x) = p(y=1 | x) ^ {\delta_{y=1}} p(y=0 | x) ^ {\delta_{y=0}} = g(w^Tx) ^ {\delta_{y=1}} (1 - g(w^Tx)) ^ {\delta_{y=1}} 
$$

* To estimate $w$, we can use a cost function equal to the negative log-likehood function (maximum likelihood): 

$$
J(w) = -l(w) = \frac{1}{n} \sum_{i=1}^n (-\delta_{y^{(i)}=1} \log (g(w^Tx^{(i)})) - \delta_{y^{(i)}=0} \log (1 - g(w^Tx^{(i)})))
$$

* There is no closed form solution so we must use gradient descent to find the maximum likelihood solution.

## Softmax Regression
* Similar to logistic regression, but for multiclass. Assum that there are $K$ classes. 
* In softmax regression, we assume $y | x$ is a categorical distribution parameterized by $g(w^Tx)$
  * $g$ must be a vector of dimension $K$ and add up to one. We can use the softmax function.
 
* The softmax function is given by

$$
g(z)_j = \frac{e^{z_j}}{\sum_{k=1}^K e^{z_k}}
$$

