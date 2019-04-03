## Reasoning Under Uncertainty

- Agents do not know everything
- decisions made in absence of information or in noisy information

Frequentist vs Bayesian

- Frequentist: looks at what has happened, only uses history, and uncertainty is pertaining to the world
- Bayesian: looks at own belief which is based on previous experiences, uncertainty is pertaining to knowledge

Bayesian would look at all data to make belief choices, frequentist would just look at own past data

### Features

- Describe World is described in states
  - or as product of a set of features (attributes/random variables)
- Number of states: $2^\text{number of binary features}$
- Factorize to get to feature values

Note: Probability is the measure of ignorance

Independence can reduce the numbers needed to calculate probability distributions

Note: $P(x|y)$ is probability of X = x given Y = y

### Rules

Bayes Rule: $P(A|B) = P(B|A)P(A)/P(B)$ since $P(A, B) = P(A|B)P(B)$

Independence -> $P(A) = P(A|B)$
