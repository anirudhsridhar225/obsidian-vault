A connected, acyclic graph is called a ***Tree***.

# Properties of trees
1. A simple graph $G$ is a tree $iff$ there exists a unique path between every pair of vertices.
2. A tree with $n$ vertices has $(n-1)$ edges.
3. Any connected graph that has $n$ vertices and $(n-1)$ edges is a tree.
4. Same for any acyclic graph.

# Binary trees
- Trees in which the parent vertex (root node) has no more than 2 children.
- A binary tree is a *full* binary tree if every internal vertex has exactly 2 children except the terminal vertices.
- Binary Tree: internal vertices degree 2 or 3
- Perfect binary tree: internal vertices degree 3

## Properties
1. The number of vertices in a full binary tree is odd and the number of _pendant_ vertices (terminal) in the same is equal to $(n+1)/2$.
2. Min height $h$ = $[log_2(n+1) - 1]$ where $[n]$ denotes the smallest integer greater than or equal to n ($ciel(n)$).