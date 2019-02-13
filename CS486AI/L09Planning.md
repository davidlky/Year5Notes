## L06, 1/30 Planning under certainty

MIU puzzle -> not possible

- Planning is finding sequence of actions to solve goals
- partial function: ???
- preconditions: specify when action can be carried out


State performs Action -> resulting state

Features: variables
Actions

Feature Based representation of actions:
- For each action, **precondition** specifies when action can be carried out
- For each feature: 
  - causal rules: specifies when feature get new value
  - frame rules: specifies when feature keeps its value
- X -> X', actions are lower case

STRIPS
- action centric: specifies effects and preconditions for each action
  - precondition -> when should it be carried out
  - effect: set of assignments of values to features that are made true

### Planning

Given: description of effects and precondition, initial states, goals: find sequence of actions

Idea: search in state-space graph

Regression Planning
- search backwards from goal: nodes are subgoals and arcs to actions

Improving Efficiencies
- define a heuristic function that estimates how hard it is to solve the goal from initial state

compare forward and regression planners
- depend on branching factor and heuristics

Planning as CSP
- search over horizons (frontier)
- for each horizon: create a CSP constaining possible actions and features

### Constraints Types
- state: between variable at the same time step
- precondition: between state and action variable that specifies what is available
- effect: state and action at `t`, and state variable at `t+1`
- frame: effect constraints that says variable does not change
- initial state: domain constraints on initial state
- goal: constraints final state