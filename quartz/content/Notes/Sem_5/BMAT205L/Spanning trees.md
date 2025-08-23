Subgraph that contains every vertex of the main graph.

![[Pasted image 20241129014357.png]]

# Properties
1. Every connected graph has at least 1 spanning tree.
2. Branch of T - edge of ST
3. Chord of T - edge not in ST
4. Rank $r$ = number of branches
5. Nullity $\mu$ = number of chords

# Minimum spanning tree
Spanning tree with smallest weight in a weighted graph $G$.

Algorithms: 
1. Kruskal's Algorithm
2. Prim's Algorithm

# Prim's Algorithm
#prims
1. Draw n isolated vertices and label them as $v_1$, $v_2$, ...., $v_n$.
2. Create a nxn matrix with entries as the weights.
3. Start from $v_1$ and connect it to it's nearest neighbor (smallest entry) say $v_k$.
4. Consider $v_1$ and $v_k$ as a subgraph and connect them to it's closest neighbor and keep going till we get $n-1$ edges.

# Kruskal's Algorithm
#kruskals
1. List all the edges acc to increasing weight.
2. Select the edge with the smallest weight in $G$.
3. For each successive step, select another smallest edge which does not create any cycle with the selected edges.
4. Continue till $n-1$ edges are selected.
