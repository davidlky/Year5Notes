# L14, Planning Under Uncertainty

## Preferences:

- Action result in outcomes, agent would prefer certain outcomes
- Decision-theoretic rational agent will do action that give the best outcome fro them

  - Sometimes don't know outcome, but will need to compare

![image](./images/19.png)

### Lotteries

- Agent may not know the outcome of their actions, but only have a probability distribution over outcomes: outcome $o_i$ at probability $p_i$

### Properties

- Completeness: Agents must act, hence they need preferences
- Transitivity: if one is better than another, which is better than another, then it carrys forward etc.
- Monotonicity: Choose larger chance at getting outcome instead of a smaller chance.
- Continuity: at some point in probability, the worse option, being more probable, is preferred
  - A > B > C, at some point p, [p: A, 1-p:C] is indifferent to B.
- Decomposability: no fun in gambling, same probabilities and same outcome then the agent should not care.
- Substitutability: if a and b are indifferent, then lotteries between them is decomposable (no preferences) too then.

### Theorem

- Preference can then be measured by a "utility" function
  - utility: outcomes -> [0,1]
  - It is linear with probabilities so that you can multiply them together
- Utility = $\sum_i p_i \times utility(o_i)$

## Rationality vs Irrationality

- Rational Agents act to maximize expected utility (humans are not the most rational of beings sadly)
  - the max overall utility is the best option!

### Prospect Theory

- We such at being rational at looking at gains vs losses
- Shown also through Framing Effect

## Making Decisions

- Agent should make decisions based on
  - ability: what are the options available
  - beliefs: what is the situation given knowledge of the agent, this updates based on what the agent senses
  - preferences: what the agent wants

Single Decisions

- Decision variable are like random variable that agent gets to choose value of
  - Expected Utility of decision $D=d_i$ leads to outcome $w$ where $e(u|D=d_i) = \sum P(w|D=d_i)u(w)$
- Optimal Single Solution: $D=d_{max}$ where expected utility is maximal!
  - $e(u|D=d_i) = \max P(w|D=d_i)u(w)$

## Decision Network

A Decision Network is a graphical representation of a finite sequential decision problem

- Extension of belief networks to include decision variables and utility
- Specifies what information is available when agent has to act.

### Network Objects

- Circle -> Random Variable, Arcs represent probabilistic dependence
- Square -> Decision Variable, Arcs represent information available when decision is made
- Diamond -> Utility, Arcs represent variable that utility depends on

### Finding Optimal Decision

- Create a Factor for each CPT and Utility
- Multiply and Sum Out all random variables
- This gives factor on Decision variables D
  - Choose maximum value in Factor!

* For Sequential Decisions: Agent act, observe, act, observer (repeat)
  - subsequent action always based on what was observed (which is caused by previous actions)

## Sequential Decision Problems

- Sequence of decision variables
- Each $D_i$ has a information set of variables -> $parents(D_i)$ -> value known at time of decision
- Policy specify what agent should do under each circumstance
  - Sequence of decision functions
  - Observe parent first, then can do child.

### Expected Utility of Policy

- Possible world $w$ satisfy policy means that policy assigns same value as the world
- The expected utility is the sum of all worlds that satisfy policy:
  - $\sum u(w) \times P(w)$
- The optimal policy is the highest utility

![image](./images/20.png)

Example

![image](./images/21.png)
