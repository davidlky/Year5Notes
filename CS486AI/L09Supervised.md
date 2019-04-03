# 1/30, Supervised Learning

Learning

- Improve behavior based on experience
- improve accuracy/range of actions or speed

Any Learning Problem: task, data, measure of improvement

Representation

- Deduction -> Draw from knowledge (top down)
- Induction -> Infer representation from data (bottom up)

## Common Learning Tasks

Supervise Learning -> given pre-classified training example, classify new ones

Unsupervised Learning -> Find natural classes for examples

Reinforcement learning - learning is delayed because of reward system at times

Transfer/Active/Inductive Language

- Learning Tasks are characterized by feedback given to learner

- Measure of success on new data, not training examples
- Biases - tendency to prefer on hypothesis over another
  - needed to make predictions on unseen data
  - deciding on a bias is hard

Given a representation and bias -> problem of learning is basically search.

Learrning -> Search through space of possible representations for best representation(s) that fit the data (using bias)

- Search spaces are too large for systematic search

### Learning Algorithm

- search space, evaluation function and search method

Data is not perfect:

- Some features are assigned wrong value
- Incomplete feature set for classification
- Missing features

Overfitting: distinction appears in data but not in unseen examples

- caused by random correlations

### Supervised Learning

- Given:

  - Input Features $X_1, ..., X_n$
  - Target Features $Y_1, ..., Y_n$
  - Set of training examples -> values for input feature and target features are given
  - Test Example -> where only input features are given

- Predict value for target feature for the test examples
  - Classification: discrete $Y$ values
  - Regression: continuous $Y$ values

### Evaluating Predictions

- $Y$ is a feature, $e$ is an example
- $Y(e)$ is the real value
- $\hat{Y}(e)$ is the predicted value
- Error -> how close the values are

#### Measuring Errors

- Absolute Error -> Sum of all absolute differences $|Y-\hat{Y}|$
- Sum of Squares Error -> Sum of all differences squared ${(Y-\hat{Y})}^2$
- Worst case Error (Max Abs diff)

Cost Based Error -> take into account of various errors

Likelihood of the data and "entropy" (negative log likelihood)

![image](./images/6.png)

### Basic Models for Supervised Learning

Many learning algo are derived from decision trees, linear classifiers and Bayesian classifiers

Learning Decision Trees

- Represented by a decision tree -> Bias towards simple decision tree!
- Search through space of decision trees, from simple to more complex ones

- Simple, successful technique for supervised learning from discrete data
  - Nodes are input attributes/features
  - Branches are labeled with input feature values
  - Leaves are predictions for "Target" features
  - Can have many branch per node
  - Branches can have many feature values

![image](./images/7.png)

### Learning a Decision Tree

- Incrementally split training data
- Solve subproblems
- Hard: how to split data?
- Criteria for good decision tree:
  - small decision tree
  - good classification (from training data, low error)
  - good generalization (from testing data, low error)

```js
\\ Input X, Output Y, Test Data E
\\ Function returns a tree <X, T_1, ..., T_n> where T's are decision trees

func DecisionTreeLearner (X, Y, E){
  if (<Stopping Criteria>){
    return PointEstimate(Y, E);
  }else{
    select X_i from X
    for (val x_j of X_i){
      E_i = All E where X_i = x_j;
      T_j = DecisionTreeLearner(X\{X_i}, Y, E_i);
    }
    return <X_i, T_1,...,T_j>
  }
}
```

### Difficulties

1. Stopping Criteria
   - How to decide to stop splitting?
   - No more features or when performance on training data is good enough
2. Selection of Features
   - Want to choose feature so that smallest tree happen
   - Actual: Myopicallu split -> allowed one split, which feature gives the best
   - heuristics
     - Most even split
     - Maximum information gain
     - GINI index etc.

Aside: Information Theory

- Bit are binary
- n bit can distinguish $2^n$ items
  - Can use probability to determine what is the expected bits needed
- Need $-log_2(P(x))$ to encode $x$
- Each symbol needs $-P(x)log_2(P(x))$
- Transmitting an entire sequence we need average: $\sum_x(-P(x)log_2(P(x)))$
  - Information Content (Entropy)
- Information Gain
  - We can use this to calculate maximum information gain!
  - Given set E of N training samples with output feature Y$P(Y=y_i) = P(y_i) = \frac{N_i}{N}$
  - Total Information Content: $I(E) = \sum_{y_i}(-P(y_i)log_2(P(y_i)))$
  - We want to find the maximum difference between $I(E) - I(E_{split})$
    - Maximum information gain!!
  - ie. if E was split up in to $E_1$ and $E_2$, $I(E_{split}) = \frac{N_1}{N}I(E_1) + \frac{N_2}{N}I(E_2)$

1. Point Estimate (final value at leaf)
   - Just return the point estimate (mean, median, most likely classification etc.)
2. How to reduce # of branches

## Use a Priority Queue

Sort leaves using a PQ ranked by information gain with best feature at each leaf -> expand only the top of queue first!

- still store as tree, but basically when going through values, only check the best information gain and expand it (so not all subtree are expanded in that order with all choices done)

![image](./images/8.png)

### Overfitting

- When there lacks data, and it will not generalize well as we found correlation when there should not be. The more complex the tree, the more overfitting can likely happen.
- Avoiding them
  - Penalty to complexity
  - Add some prior data
  - Cross validation
- Error can be caused by

  - Bias -> representation bias (too simple), seach bias (not enough depth)
  - variance -> lack of data
  - noise -> process generating data is bad
  - bias variance trade off -> both

- Capacity: capacity of model is ability to fit a wide variety of function: inverse of bias -> high capacity model has low bias!

#### Cross Validation

- split training data into training and validation set!
  - have a pretend test set!
  - optimize to perform well on validation set
  -
