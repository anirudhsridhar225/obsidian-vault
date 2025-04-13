Graph plan algorithm

```pseudocode
function graphPlan(problem) returns solution or failure
	graph <-- initial-planning-graph(problem)
	goals <-- Goals(problem)
	loop do
		if goals all non-mutex in last level of graph then do
			solution <-- extract-solution(graph, goals, length(graph))
			if solution != failure then return solution
			else if no-solution-possible(graph) then return failure
		graph <-- expand-graph(graph, problem)
```
