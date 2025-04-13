Forward State Space Search

- We start at the initial state and go towards the final state.
- While doing that, we have to consider the probable effects of actions taken at every state.
- The algorithm takes as input the statement `P = (O, s0, g)` of a planning problem P (O is a list of actions).
- if P is solvable then FSSS(O, s0, g) returns a solution plan, otherwise returns failure.

# Algorithm
1. compute whether current state is goal or not
2. find set of all actions that are applicable to current state
3. compute a successor state that is the result of applying an action
4. proceed to successor state
5. repeat from step 1

# Problem Formulation
1. Initial state
2. Actions:
	1. Applicable to curr state
	2. Add positive literals to add list and negative literals to delete list
3. Goal test:
	- Whether state is goal or not
4. Step cost:
	- either given or assumed as 1 for each action
