Partial Order Planning

- a planner that can represent plans in which some steps are ordered wrt each other and other steps are unordered
- only specifies order when necessary
- works on several subgoals independently
- solves them with subplans and combines them
- leaves actions unordered unless they MUST be sequential 
 ![[{E301C6B8-3C39-43A9-948E-D7CE5530A4B0}.png]]

# Consistent plan
- a plan that has
	- no cycle in the ordering constraints
	- no conflicts with the causal links
- solution is a consistent plan with no open preconditions

# Setting up the POP
1. Add dummy states
	1. Start
		- has no preconditions
		- it's effects are the literals of the initial state
	2. Finish
		- it's preconditions are the literals of the goal state
		- has no effects
2. Initial Plan
	1. Actions: {Start, Finish}
	2. Ordering Constraints: {Start before Finish}
	3. Causal links: {}
	4. Open Preconditions: {`<As needed>`}