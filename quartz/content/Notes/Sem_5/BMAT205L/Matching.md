A _Matching graph_ is a subgraph of a graph where there are ***no*** edges adjacent to each other. It is also termed as such because there shouldn't be any vertex in common between any two pairs of edges.

			A Matching in G is a set of independent edges.

## Maximal Matching
A maximal matching is a matching to which no edge in the graph can be added.

## Maximum Matching
A matching $|M|$ of $G$ is maximum is $G$ has no matching $M_0$ with $|M_0| > |M_1|$. It can also be determined as the `maximal matching with maximum number of edges`.

The number of edges in the maximum matching of $G$ is called it's Matching Number $M(G)$.

## Perfect Matching
A matching $M$ is said to be a perfect matching if every vertex of $G$ is $M$-saturated.

Alternatively, A matching of $G$ is said to be perfect if every vertex of $G$ is incident to exactly one edge of the matching.

## Theorems
1. Let $G$ be a $k$-regular bipartite graph with $k$ > 0. Then $G$ has a perfect matching.
	This implies that if a graph $G$ has a perfect matching, then the number of vertices is even. `The converse does not hold.`