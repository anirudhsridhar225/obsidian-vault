#### Given a maze. solve it
#backtracking

```java

import java.util.Scanner;

public class Main {
	public void printSolution(int sol[][], int n) {
		for (int i= 0; i < n; i++) {
			for (int j= 0; j < n; j++) {
				System.out.print(" " + sol[i][j] + " ");
			}
			Sysmtem.out.println();
		}
	}

	public boolean isSafe(int maze[][], int x, int y, int n) {
		return (x >= 0 && x < n && y >= 0 && y < n && maze[x][y] == 1);
	}

	public boolean solveMaze(int maze[][], int n) {
		int sol[][] = new int[n][n];

		for (int i= 0; i < n; i++) {
			for (int j= 0; j < n; j++) {
				sol[i][j] = 0;
			}
		}

		if (!solveMazeUtil(maze, n, 0, 0, sol)) {
			System.out.println("soln doesnt exist");
			return false;
		}

		return true;
	}

	public boolean solveMazeUtil(int maze[][], int n, int x, int y, int sol[][]) {
		if (x == n-1 && y == n-1) {
			sol[x][y] = 1;
			return true;
		}

		if (isSafe(maze, x, y, n) == true) {
			sol[x][y] = 1;

			if (solveMazeUtil(maze, n, x+1, y, sol)) {
				return true;
			}

			if (solveMazeUtil(maze, n, x, y+1, sol)) {
				return true;
			}

			sol[x][y] = 0;
		}

		return false;
	}

	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int maze[][] = new int[n][n];

		for (int i= 0; i < n; i++) {
			for (int j= 0; j < n; j++) {
				maze[i][j] = sc.nextInt();
			}
		}

		if (solveMaze(maze, n)) {
			System.out.println("Solution exists");
			printSolution(maze, n);
		}
	}
}
```