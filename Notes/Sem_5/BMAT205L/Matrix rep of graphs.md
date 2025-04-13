2 types of matrixes:
1. Incidence matrix
2. Adjacency matrix

# Incidence matrix
If $G$ is an undirected graph with n vertices and m edges then the $nXm$ matrix $B$ = $[b_{ij}]$ is
![[Pasted image 20241129030800.png]]

![[Pasted image 20241129030920.png]]


# Adjacency matrix
If $G$ is an undirected graph with n vertices then the $nXn$ matrix $A$ = $[a_{ij}]$ is
![[Pasted image 20241129030855.png]]

![[Pasted image 20241129030936.png]]


# Theorems
1. <u>Number of walks of length $r$ between any two vertices.</u>
	If A is the adjacency matrix of a graph $G$, then the number of different walks of length $r$ from $v_i$ to $v_j$ is equal to the $(i,j)^{th}$ entry of $A^r$.