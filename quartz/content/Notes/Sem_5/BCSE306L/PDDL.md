Planning domain description language

- Allows to define a world in which:
	1. The planning world is described.
	2. Possibilities of actions are described (as schemas).
	3. Describes current states and objectives using constructs defined in schemas.

![[Screenshot 2024-11-24 at 6.25.13 PM.png]]
Above shown is the initial and final state of the block world.

##### We shall describe the block world in pddl now:

1. Blocks (domain)
```pddl
(define (domain Blocks)
	(:requirements :typing)
	(:types block)
)
```

2. Predicates (used to describe the situation)
```pddl
(:predicates (on ?x - block ?y - block)
	(onTable ?x - block)
	(holding ?x - block)
	(clear ?x - block)
	(armempty)
)
```

3. Action description for pickup()
```pddl
(:action pickup
	:parameters (?x - block)
	:precondition (and (ontable ?x) (armempty) (clear ?x))
	:effect (and (not (armempty)) (holding ?x) (not (onTable ?x)))
)
```

4. Action description for putDown()
```pddl
(:action putDown
	:parameters (?x - block)
	:precondition (holding ?x)
	:effect (and (onTable ?x) (armempty))
)
```

5. Problem instance description for block world
```pddl
(define (problem blocksProblem)
	(:domain Blocks)
	(:objects
		A - block
		B - block
		C - block
	)
)

(:init
	(onTable A)
	(onTable B)
	(on C A)
	(clear B)
	(clear C)
	(armempty)
)

(:goal
	(and
		(on A B)
		(on B C)
	)
)
```
