
#### Count all the possible paths from top left to bottom right of a mxn matrix with the constraints that from each cell you can either move only to the right or downwards.

```java
import java.util.Scanner;

public class Main {
	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		int m = sc.nextInt();
		int n = sc.nextInt();
		sc.close();

		System.out.println(totalPaths(m, n));
	}

	public static int totalPaths(int m, int n) {
		if (m == 1 || n == 1) {
			return 1;
		}

		return totalPaths(m-1, n) + totalPaths(m, n-1);
	}
}
```