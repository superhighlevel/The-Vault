---
aliases: Cost function, Loss function, L(.)
---
#### The Lost function
   **A loss function** is a function that compares how far off a [[Prediction]] is from its [[targets]] for [[Observations]] in the training data. Given a target and its prediction, the loss function assigns a scalar real value called the loss. The lower the value of the loss, the better the model is at predicting the target. We use *L* to denote the loss function
#### The Cost function
The [[Cost function]] is of the form $L(y^∗,f(x; θ))$. $L(.)$ is often designed as a *smooth function of error*, and is differentiable w.r.t. θ. A commonly used cost function that meets these criteria is the [[mean squared error (MSE)]],