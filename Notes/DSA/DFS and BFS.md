
## What do they mean?

DFS stands for depth first search. Similarly, BFS stands for breadth first search. The general idea is to search and visit every node in the graph.

BFS goes through every node in the present level before moving to the next level. it can be implemented with a queue.

DFS on the other hand goes through to the neighbour with the max depth immediately before coming back up and going to the next node. This is usually implemented using recursion and is the easier of the two, but it can be done with a stack as well.

## Coding them

### for an adjacency list

```python
from collections import deque

def bfs(start, adj):
    visited = set()
    q = deque([start])
    visited.add(start)

    while q:
        node = q.popleft()
        print(node, end=' ') #handle visiting the node as needed

        for nei in adj.get(node, []):
            if nei not in visited:
                visited.add(nei)
                q.append(nei)

def dfs(start, adj):
    visited = set()

    def util(node):
        visited.add(node)
        print(node, end=' ') #handle visiting the node as needed
        
        for nei in adj.get(node, []):
            if nei not in visited:
                visited.add(nei)
                util(nei)

    util(start)
```

```java
import java.util.*;

public void bfs(Map<String, List<String>> adj, String start) {
    Set<String> visited = new HashSet<>();
    Queue<String> q = new LinkedList<>();

    q.add(start);
    visited.add(start);

    while (!q.isEmpty()) {
        String node = q.poll();
        System.out.print(node + ' ');

        for (String nei: adj.getOrDefault(node, new ArrayList<>())) {
            if (!visited.contains(nei)) {
                visited.add(nei);
                q.add(nei);
            }
        }
    }
}

public void dfs_helper(Map<String, List<String>> adj, String node, Set<String> visited) {
    visited.add(node);
    System.out.print(node + " ");

    for (String nei: adj.getOrDefault(node, new ArrayList<>())) {
        if (!visited.contains(nei)) {
            dfs_helper(adj, nei, visited);
        }
    }
}

public void dfs(Map<String, List<String>> adj, String start) {
    Set<String> visited = new HashSet<>();
    dfs_helper(adj, start, visited);
}
```
