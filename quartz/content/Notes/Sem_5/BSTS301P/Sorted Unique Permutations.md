
#### Given a string of length n, print all possible unique permutations of that string in sorted order.

<u><b>Logic</u></b>: 
- for string of length n, total number of permutations = *n!*
- for string of length n in which 1 character repeats m times, total number of permutations = *n!/m!* 

<u><b>Steps</u></b>:
- Sort given string
- Calculate number of permutations, say *i*
- Print sorted string
- Loop for *i-1* times and find next greater string and print that

<u><b>Code</u></b>:

```java
import java.util.Arrays;
import java.util.HashSet;
import java.util.Scanner;
import java.util.Set;

public class Main {
	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		String input = sc.nextLine();
		sc.close();

		distinctPermutations(input);
	}

	public static void distinctPermutations(String input) {
		char[] chars = input.toCharArray();
		Arrays.sort(chars);
		input = new String(chars);
		permute(input.toCharArray(), 0);
	}

	public static void permute(char[] chars, int index) {
		if (index == chars.length - 1) {
			System.out.println(String.valueOf(chars));
			return;
		}

		Set<Character> used = new HashSet<>();
		for (int i= index; i < chars.length; i++) {
			if (used.contains(chars[i])) {
				continue;
			}

			used.add(chars[i]);
			swap(chars, index, i);
			permute(chars, index+1);
			swap(chars, index, i);
		}
	}

	public static void swap(char[] chars, int i, int j) {
		char temp = chars[i];
		chars[i] = chars[j];
		chars[j] = temp;
	}
}
```