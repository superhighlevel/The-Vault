### Common Supervised Learning Metrics
Once a model is trained, it can be tested on a hold-out dataset to have an estimate of its generalization performance. Suppose the model is $f(·; θ)$, and the  hold-out set contains N data points: $D = {(x_1,y_{1}^*),(x_2,y_{2}^*),...,(x_{N},y_{N}^*)}$.
#### Regression problems
The first metric is the aforementioned mean squared error that is appropriate for [[regression problems]] (i.e., $y_i^∗$ is considered real-values):
![[mean squared error (MSE)#MSE]]
#### Classification problems
For [[classification problems]], $y_i^*$ takes values from a finite set viewed as categories. For simplicity, assume $y_i^* ∈ {+1,−1}$ here, so that an example $(x_i,y_i^*)$ is called positive (or negative) if $y_i^*$ is  $+1$ (or $−1)$. The following metrics are often used:
![[Accuracy#Accuracy]]
![[Precision#Precision]] 
![[Recall#Recall]]
![[F1 Score#F1 Score]]
