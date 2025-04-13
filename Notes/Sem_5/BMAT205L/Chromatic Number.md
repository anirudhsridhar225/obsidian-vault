
# Chromatic Polynomial 

$f(G, λ)$ is the chromatic polynomial of a graph $G$ on $n$ vertices equal to the number of ways you can color the graph using at most $λ$ colors.

## Theorems

1. For path and trees: A graph is a tree of a path of $n$ vertices $iff$ it's chromatic polynomial is 
					$f(G, λ) = λ(λ)^{n−1},λ >= 2$  

2. For an empty graph G on n vertices, then
					$f(G,λ) = λ^n$

3. For a complete graph $K_n$ on n vertices then
					$f(K_n,λ) = λ(λ-1)(λ-2)...(λ-(n-1))$

4. For a disconnect graph G with n components,
				   $f(G,λ) = f(G_1,λ)*f(G_2,λ)*.....*f(G_n,λ)$

# Decomposition Theorem

Let $e$ be any edge in $G$, where $u$ and $v$ are end vertices of $G$. Let $Ge$ be a graph obtained by deleting an edge $e$ from G. Let $G_e'$ be a simple graph obtained from $G$ by fusing the vertices $u$ and $v$ together and replacing sets of parallel edges with single edges, then

							$f(G,λ) = f(Ge,λ) - f(Ge',λ)$


# Matching

A _Matching graph_ is a subgraph of a graph where there are ***no*** edges adjacent to each other. It is also termed as such because there shouldn't be any vertex in common between any two pairs of edges.

			A Matching in G is a set of independent edges.

## Maximal Matching
A maximal matching is a matching to which no edge in the graph can be added.

## Maximum Matching
A matching $|M|$ of $G$ is maximum is $G$ has no matching $M_0$ with $|M_0| > |M_1|$. It can also be determined as the `maximal matching with maximum number of edges`.


## Perfect Matching
A matching $M$ is said to be a perfect matching if every vertex of $G$ is $M$-saturated.

Refer [[Matching]].

# Covering

A covering in a graph is a subgraph that either contains
- All vertices --> Edge covering
- All edges --> Vertex covering
corresponding to some other graph.

Refer [[Covering]]
