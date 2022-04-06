---
aliases: mini-batch Stochastic Gradient Descent (SGD), SGD
---
Mini-batch Stochastic Gradient Descent (SGD) is an [[optimization|Optimizer]] use for update the $\theta$
#### mini-batch Stochastic Gradient Descent (SGD)
One of the most widely used [[optimization]] procedure for [[Deep Learning|Deep Learning]]
**Mini-batch Stochastic Gradient Descent (SGD)** updates θ after each [[batch]] as:
$$\theta \leftarrow \theta - \dfrac{\alpha}{N}\sum_{i=1}^{N}\nabla_{\theta}L(y_{i}^*, f(x_i;\theta)),$$
* Where:
	* $\nabla_{\theta} L(.)$ is the standard [[backpropagation]]
	*  $N$ is the [[batch size]] and
	*  $\alpha$ is the [[learning rate]] 