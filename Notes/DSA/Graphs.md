
# How to represent a graph

there are 2 ways: adjacency list and adjacency matrix

## adjacency list

```python
class Graph:
    def __init__(self):
        self.adj = {}

    def add_edge(self, u, v):
        self.adj.setdefault(u, []).append(v)
        self.adj.setdefault(v, []).append(u)  #if undirected

    def print_graph(self):
        for node in self.adj:
            print(node, " -> ", self.adj[node])
```

```java
import java.util.*;

class Graph {
    private static Map<String, List<String>> adj = new HashMap<>();

    public static void addEdge(String u, String v) {
        adj.putIfAbsent(u, new ArrayList<>());
        adj.putIfAbsent(v, new ArrayList<>());
        adj.get(u).add(v);
        adj.get(v).add(u); //if undirected graph
    }

    public static void printGraph() {
        for (var node: adj.keySet()) {
            System.out.println(node + " -> " + adj.get(node));
        }
    }
}
```

## adjacency matrix

```python
class Graph:
    def __init__(self, size):
        self.size = size
        self.adj = [[0]*size for _ in range(size)]

    def add_edge(self, u, v):
        self.adj[u][v] = 1
        self.adj[v][u] = 1 #if undirected graph

    def print_graph(self):
        for row in self.adj:
            print(row)
```

```java
import java.util.*;

public class Graph {
    private static int[][] adj;
    private static int nodes;

    public Graph(int n) {
        nodes = n;
        adj = new int[n][n];
    }

    public static void addEdge(int u, int v) {
        adj[u][v] = 1;
        adj[v][u] = 1;
    }

    public static void printGraph() {
        for (int i= 0; i < adj.length; i++) {
            for (int j= 0; j < adj[0].length; j++) {
                System.out.println(adj[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

## graph algorithms

[[DFS and BFS]]
[[Bellman Ford]]
[[Djikstra's Algorithm]]
[[Floyd Warshall]]
[[Kahn's Algorithm]]
[[Prims and Kruskals]]
