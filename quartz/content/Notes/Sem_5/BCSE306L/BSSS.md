Backward State Space Search

- We start at the goal state instead of the initial state and move backwards towards the initial state
- Everything else is similar to [[FSSS]]

# Algorithm
1. Start at goal
2. Check if goal is initial state
3. If not, apply inverses of the planning operators to produce subgoals
4. If set of subgoals produced satisfies initial state, stop and return