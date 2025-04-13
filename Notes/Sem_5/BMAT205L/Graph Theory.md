A graph is an ordered tuple $(V(G);E(G))$ where $V(G) = {v_1,v_2,v_3,...,v_n}$ is a nonempty set and elements of this set are called vertices, $E(G)$ is an 2-element subset of $V(G)$ and the elements of $E(G) = {e_1,e_2,e_3,...,e_m}$ are called edges of G.

***Simple graph***: graph with no loops or edges
***Multi graph***: graph with multiple edges connecting the same pair of vertices
***Psudeo graph***: graph with multiple edges and loops

![[Pasted image 20241129030007.png]]

***Trivial graph***: graph with only one vertex
***Null graph***: graph with no edges
Note: every trivial graph is a null graph but the converse is not true

#### Theorem
For a graph $G = (V,E)$, the sum of the degree of all vertices = $2m$, where $m$ is the number of edges in $G$.