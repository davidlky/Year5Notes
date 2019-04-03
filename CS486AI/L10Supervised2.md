### Supervised ML II

Linear Regression

- Output is a linear function of input feature
- Goal is to find weights that minimizes Error(E, $\bar{w}$)
  - $\bar{w} = w_0, w_1, ..., w_n$ <- weights
  - The sum of squares error $\sum_{e \in E}(Y(e)-\har{Y}(e))^2$

Gradient Descend

- find minimum analytically through gradient descent -> a step size/learning rate
- incremental -> go through each $e$ iteratively
- stochastic -> chosen $e$ randomly
- Batched -> process batch of size $n$ before updating weights
  - if $n$ is all data -> gradient descent
  - if $n=1$ -> incremental

### Linear Classifier

- No point making prediction of less than 0 or greater than 1 for binary classification i.e.
- f -> activation function
  - for example f(x) = {1, 0} wrapped around $\hat{Y}$
  - sigmoid -> S shaped

### Linearly Separable

- if there's a hyperplane where classification is true on one side and false on other side -> Linearly Separable!
  - Also can be multi linearly separable
- Kernel Trick - Mercer's Theorem
  - Dot product in the new space = function(points) in old space -> Kernel
  - We dont need to know the exact transformation we only need to know how to compute the Kernel value (Kernel is the new dimension)

### Support Vector Machines

- Also uses Kernel trick to give it seperations on hyperplanes

Neural Networks

- connect many simple units
- Errors made are propagated backwards to change weights (back propagation)
- many layers

Neural Network Basics

- each node receives set of inputs and already has a set of weights
  - weights = number of parents + 1 (since $w_0=1$ from Lin Reg)
  - output is the activation function output
    - activation: step, sigmoid, rectified linear

Deep Neural Network just has multiple layers of these functions and temp Lin Reg results

#### Back propagation

- stochastic gradient descent (random chosen) with learning rate

- Skipped???

### Composite Models

- Random Forests
  - Each decision tree is different, different feature/splitting criteria and training set
- Ensemble learning
  - combination of base level algorithms
- Boosting: sequence of learning
  - each learner trained to fit examples that the previous is bad at
  - early, allow false positive, but eliminate true possitive
  - later, harder problem, but set of example more focused
