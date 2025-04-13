- Stanford Research Institute Problem Solver
- It is an automated planning technique used to find a goal by executing a domain from the initial state of the domain.
- To describe the world, we use 2 types of terms:
	1. States- initial and goal
	2. Action Schema- objects, actions, preconditions and effects
- once the world is described then provide a problem set, described by:
	1. initial state
	2. goal condition
# State representation
- States are conjunctions of ground, function-free and positive literals.
- Closed-world is assumed when describing states, i.e. the world model contains everything that the agent needs to know.

# Goal representation
- Goals are conjunctions of literals, can have variables as well.
- A goal may represent more than one state.

# Action representation
- They are represented by preconditions that must hold before execution and the effects after execution.

# STRIPS Action Schema
An action schema includes:
1. Action name and parameter list
2. Precondition: conjunction of function-free positive literals. The action variables must also appear in precondition
3. Effect: a conjunction of function-free literals (positive or negative)

# Block world problem using STRIPS
![[{E8D748CF-88BB-49FF-A031-0D5A73C367D5}.png]]

S0 --> S1 --> S2 --> g
### S1
- `On(A, table)`
- `On(B, table, C)`
- `On(C, table)`
- `Clear(A)`
- `Clear(B)`
- `Clear(table)`

### S2
- `On(A, B)`
- `On(B, C)`
- `On(C, table)`
- `Clear(A)`
- `Clear(table)`

