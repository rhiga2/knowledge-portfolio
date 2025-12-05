Logistic and Softmax Regression
===============================
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
