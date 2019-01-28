## L03 (Lecture 2), 1/12

Agent perform actions to affect the enviornment
- makes decisions based on abilities, goals/prefernces, prior knowledge, stimuli and past experiences

Knowledge Representation - Symbol Systems
- Symbol is a meaningful physical pattern that can be manipulated
- Symbol system: create, copies, modifies and destroys symbols
- Physical Symbol System Hypothesis:
  - a PSS has the necessary and sufficient means for general intelligent action
    - AI on computer is possible in theory, but not feasible in practice

Good representation:
- Expressive, close to problem (compact and maintainable), amenable to efficient computation, amenable from more input

Decision making for AI
- Abilities: what can it do
- Observations: direct input from environment
- Prior Knowledge: knowledge base when developed (map, capabilities)
- Past Experiences
- Goals

Dimensions
- Research leads to simplifying assumptions and reducing them
  - each simplification leads gives a new *dimension*
    - can be multiple values - simple to complex values
    - combine these assumptions

Much of AI is to find compact representations and exploiting it for computational gains

Agent reason in terms of
- explicit states
- features/propositions
- individuals + relations
  - feature for each relationship on tuples of individuals

Planning Horizon
- how far Agent looks into future when deciding
  - static: world does not change
  - finite stage: fixed number of time steps
  - indefinite stage: finite but not predetermined #
  - infinite: plan for going forever

Uncertainty
- what agent can determine the state from observations
  - Fully observable: know the state of world from observation
  - Partially Observable: there's many states that are possible from observation

Uncertain Dynamics
- if the agent knew initial state and action, can it predict the ending state?
  - deterministic: can be determined from action and state
  - **stochastic**: uncertainty over states resulting from action from state

Goals or complex preferences
- achievement goals: goal to be reached
- maintenance goal
- complex preferences: tradeoff between decisions

Single agent: reasoning is where agent assume other agents are part of the environment

Multiple agent: agent needs to reason about the reasoning of other agents

Knowledge can be given or learned from data or past experience

Perfect rationality: agent can determine best course of action, net of limited computational power

Bounded rationality: makes good decisions based on limitations

