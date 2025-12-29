Logistic and Softmax Regression
===============================
# Logistic Regression
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
J(w) = -l(w) = \frac{1}{n} \sum_{i=1}^n \left[-\delta_{y^{(i)}=1} \log g(w^Tx^{(i)}) - \delta_{y^{(i)}=0} \log (1 - g(w^Tx^{(i)}))\right]
$$

* There is no closed form solution so we must use gradient descent to find the maximum likelihood solution.

# Softmax Regression
* Similar to logistic regression, but for multiclass. Assum that there are $K$ classes. 
* In softmax regression, we assume $y | x$ is a categorical distribution parameterized by $g(Wx)$.
  * $g$ must be a vector of dimension $K$ and add up to one. We can use the softmax function.
  * $W$ is a matrix of size $K \times d$.
 
* The softmax function is given by

$$
g(z)_j = \frac{e^{z_j}}{\sum_{k=1}^K e^{z_k}}
$$

* Similar to logistic regression, we can use maximum likelihood to get the loss function. 

$$
p(y|x) = \prod_{j=1}^K p(y=j|x)^{\delta_{y=j}} = \prod_{j=1}^K g(Wx)_j^{\delta_{y=j}}
$$

* The cost function is given by:

$$
J(W) = - l(W) = -\sum_{i=1}^n \sum_{j=1}^K \delta_{y^{(i)}=j} \cdot \log g(Wx^{(i)})_j
$$

* Again, there is no closed form solution so we must use gradient descent to find the ML solution.

