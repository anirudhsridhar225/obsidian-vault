#### Given n people and an integer k, the problem is that the n people will be executed one by one and in each iteration the k+1th person from the current index is executed. Find the index of the person that lives.

```java
import java.util.Scanner;

public class Main {
	public static void main (String args[]) {
		Scanner sc = new Scanner(System.in);
		int n = sc.nextInt();
		int k = sc.nextInt();
		sc.close();

		System.out.println(josh(n, k));
	}

	static int josh(int n, int k) {
		if (n == 1) {
			return 1;
		} else {
			return (josh(n-1, k) + k-1)%n+1;
		}
	}
}
```