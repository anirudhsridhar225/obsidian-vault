### Overview

- Planning is the reasoning behind actions carried out or the actions that are intended to be carried out by the agent.
	- choice of action made by agent before executing them in the domain
	- <u>objective</u>: to achieve a desired outcome
	- objectives can be hard or soft constraints
- Planning algorithms are search based.


#### Difference between Simple and Hard Planning

| #                  | Simple planning  | Hard planning        |
| ------------------ | ---------------- | -------------------- |
| Domain             | Static           | Dynamic              |
| Domain             | Fully observable | Partially observable |
| Actions            | Instantaneous    | Interval based       |
| Effects of actions | Deterministic    | Stochastic           |

### Classical Planning
- Simulated the changes that an action produces in a mental model of the world
- Selects the desirable course of action based on the mental simulations
- Planning is a search through a possible combinations of actions to find a plan that will work

### Memory Based Planning
- involves representing and reasoning based on events in the past
- exploit an agent's memory and use a strategy/plan/planning experience that previously worked for a similar scenario

### Planning Domain Description Language (PDDL)
Refer [[PDDL]]

# STRIPS
Refer [[STRIPS]]

# Planning with state-space search
- it is the most straightforward approach
- has two types:
	1. Forward state-space search (or progression)
	2. Backward state-space search (or regression)

[[FSSS]]
[[BSSS]]
[[HSP]]
[[GSP]]
[[POP]]
# Planning Graph
- can be used to give better heuristic estimates
- only work for propositional problems
- nodes - propositions
  edges - actions
- approximation of a complete tree of all possible actions and their results
- input = planning problem expressed in STRIPS
  output = sequence of operations for reaching a goal state
- layered graph with alternate layers of propositions and actions
- construct from left to right
	- keep inserting actions and propositions until we get goal propositions on the proposition layer
	- goal propositions are mutually exclusive

# Components of a Plan
1. A set of actions
2. A set of ordering constraints
3. A set of causal links between actions
4. A set of open preconditions

# Threats
Causal links are used to detect if a newly introduced action interferes with past decisions. Such actions are called threats.

## Resolving threats
When a plan contains a threat, there is a danger that there will be bugs in the plan (search reaches a dead-end).

![[{5D8D1C50-0349-470D-B2D6-F3AAB54D8494}.png]]
