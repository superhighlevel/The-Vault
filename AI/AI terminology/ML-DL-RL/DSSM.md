---
aliases: DSSM, Deep Structured Semantic Models
---
#### DSSM
![[Pasted image 20220405165123.png]]
DSSM stands for Deep Structured [[Semantic Models]], or Deep [[Semantic Similarity Model]]. [[DSSM]] is a [[deep learning model]] for measuring the [[Semantic Similarity]] of a pair of inputs $(x, y)$. As illustrated in Fig. 2.3, a DSSMbconsists of a pair of [[DNN|DNNs]], $f_1$ and $f_2$, which map inputs $x$ and $y$ into corresponding vectors in a common low-dimensional semantic space. Then the similarity of $x$ and $y$ is measured by the [[Cosine Distance|cosine distance]] of the two vectors. $f_1$ and $f_2$ can be of different architectures depending on $x$ and $y$

##### Example
To compute the [[similarity]] of an image-text pair, $f_1$ can be a [[deep convolutional NN]] and $f_2$ an [[RNN]]. Let $θ$ be the parameters of $f_1$ and $f_2$ . $θ$ is learned to identify the most effective feature representations of $x$ and $y$, optimized directly for end tasks. In other words, we learn a hidden [[semantic space]], parameterized by θ, where the semantics of distance between vectors in the space is defined by the task or, more specifically, the training data of the task. For example, in Web document ranking, the distance measures the query-document relevance, and $θ$ is optimized using a [[pair-wise rank loss]].
Consider a query $x$ and two candidate documents $y+$ and $y−$ , where $y+$ is more relevant than $y−$ to $x$. Let $sim_θ(x, y)$ be the similarity of $x$ and $y$ in the semantic space parameterized by $θ$ as $$sim_\theta(x, y) = cos(f_1(x), f_2(y)).$$ We want to maximize $$\Delta=sim_\theta(x, y^+) - sim_\theta(x, y^-).$$ We do so by optimizing a smooth loss function $$L(\Delta;\theta) = log(1 + exp(-\gamma\Delta),$$
where $\gamma$ is a scalling factor, using [[mini-batch Stochastic Gradient Descent (SGD)|SGD]]. 
