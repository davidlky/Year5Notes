# L12, Learning Under Uncertainty 1

## Bayesian Learning

- Premise

  - Have a bunch of hypothesis OR models (note models are hypothesis and have distribution of prior probabilities)
  - Assume all are correct at the start
  - See which one is most correct
  - Compute the expected prediction given distribution

- Refine each model according to Data, then find Y from the given X input and the model.

- Prior = P(H)
- Likelihood = P(d|H)
  - Evidence: d = {$d_1, d_2,...$}
- $P(H|d) \propto P(d|H)P(H)$

### Predictions

- Predictions are weighted averages of the predictions of the individual hypotheses
- $P(X|d) = \sum_i P(X|h_i)P(h_i|d)$
  - Basically serves as intermediary step between data and hypothesis
- Posterior probability changes as more data comes in, and prediction of X becomes more accurate as the posterior increases.
- NOTE: A posterior probability, in Bayesian statistics, is the revised or updated probability of an event occurring after taking into consideration new information.

Bayesian Learning is:

- Optimal: given prior, Bayesian prediction is often the best one
- No Overfitting: prior/likelihood penalize complex hypothesis!

Problem: if hypothesis space large, it is very problematic

- solution: approximate Bayesian Learning

### Maximum A Posteriori

- Make prediction based on the most probable hypothesis: $h_{map}$
- $h_{map} = argmax_{h_i}P(h_i|d)$
- $P(X|d) \approx P(X|h_{map})$
- NOTE: in Bayesian Learning, all hypothesis are used!
- Obviously less accurate as it only uses 1 hypothesis
  - MAP and Bayesian will converge when data size large enough!!
- NOTE: this can still be intractable (problematic) as it will need to multiply a lot
  - i.e. $h_{map} = argmax_{h_i}P(h_i)P(d|h_i)$ and d is multiplied using each data point
  - You can take the log to linearize better, but even so, it is still very complex

### Maximum Likelihood

- Simplify on MAP, assume uniform prior
- $h_{map} = argmax_{h_i}P(h_i)P(d|h_i)$ where as $h_{ml} = argmax_{h_i}P(d|h_i)$
- $P(X|d) \approx P(X|h_{ml})$
- Obviously less accurate as it only uses 1 hypothesis and ignore all prior as well!
  - ML, MAP and Bayesian will converge when data size large enough!!
- more likely to get overfitting as prior is ignored
  - easier to find than MAP, esp looking at log linearization

### Binomial Distribution

- Generalizes the hypothesis space to be continuous
- $P(X=x) = \beta$
- $P(X\ne x) = 1-\beta$
- $P(n x, p \neg x) = (\beta)^n(1-\beta)^p$ for just 1 order
- $P(n x, p \neg x) ={n+k \choose n}(\beta)^n(1-\beta)^p$ for all orders

## Naive Bayesian Classifier

IDEA: if you knew the classification you can predict value of the features

- classification problem

- $P(Class | X_1, X_2, ...) \propto P(X_1, X_2, ... | Class)P(Class)$

Naive Bayesian Classifer:

- Assume that X's are independent of each other given a class (hence the word Naive)
- Need $P(Class)$ and $P(X_i | Class)$ for each $X_i$
- Email example, for instance (User Action -> Length, Reply, At Home etc.)

- Predict Class C based on Attribute A's

Example (email example):

- Each sub $P(X_i | Class)$ = # of times $X_i$ happen / # of times Class happened

## Minimum Description Length

- Bayesian Learning: update the posterior (update the probability given new information)
- $P(H|d) = kP(d|H)P(H)$ (k because of the $\propto$)
- We can look at this with the log model:
- $−logP(H|d) = − log P(d|H) − logP(H)$
- $log P(d|H)$ = number of bits to encode the data given the model
- $log P(H)$ = number of bits to encode the model
- MDL principle: choose model that minimize both the data encoding and the model encoding length
  - Useful for model selection!
