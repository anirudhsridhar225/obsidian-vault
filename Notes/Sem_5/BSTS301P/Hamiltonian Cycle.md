#### code to find if a graph has a hamiltonian cycle or not
- a hamiltonian cycle is one in which you start from one vertex and visit every other vertex exactly once and come back to the starting vertex

```java
import java.util.Scanner;

public class Main {
	int path[];

	public static boolean isSafe(int v, int graph[][], int path[], int pos) {
		if (graph[path[pos-1]][v] == 0) {
			return false;
		}

		for (int i= 0; i < pos; i++) {
			if (path[i] == v) {
				return false;
			}
		}

		return true;
	}

	public static boolean hamCycleUtil(int graph[][], int path[], int pos, int v) {
		if (pos == v) {
			if (graph[path[pos-1]][path[0]] == 1) {
				return true;
			} else {
				return false;
			}
		}

		for (int k = 1; k < v; k++) {
			if (isSafe(k, graph, path, pos)) {
				path[pos] = k;

				if (hamCycleUtil(graph, path, pos+1, v)) {
					return true;
				}
				
				path[pos] = -1;
			}
		}
		
		return false;
	}

	public static int hamCycle(int graph[][], int v) {
		path = new int[v];

		for (int i= 0; i < v; i++) {
			path[i] = -1;
		}
		
		path[0] = 0;

		if (!hamCycleUtil(graph, path, 1, v)) {
			System.out.println("no soln");
			return 0;
		}
		
		printSolution(path);
		return 1;
	}

	public static void printSolution(int[] path, int v) {
		for (int i = 0; i < V; i++) {
            System.out.print(" " + path[i] + " ");
        }
        System.out.println(" " + path[0] + " ");
	}

	public static void main (String args[]) {
		//input and shit cba
	}
}
```
