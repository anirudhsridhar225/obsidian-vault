#### Sorting elements in the order that seems natural to humans
- for example: "file1, file2, file10" instead of "file1, file10, file2"

```java
import java.util.ArrayList;
import java.util.Comparator;
import java.util.List;
import java.util.Scanner;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Main {
	public static void main (String[] args) {
		Scanner sc = new Scanner(System.in);
		int num = sc.nextInt();
		int buffer = sc.nextLine();
		List<String> strings = new ArrayList<>();

		for (int i= 0; i < num; i++) {
			strings.add(sc.nextLine());
		}
		sc.close();

		List<String> sortedStrings = naturalSort(strings);
		for (String str: sortedStrings) {
			System.out.println(str);
		}
	}

	public static List<String> naturalSort(List<String> strings) {
		strings.sort(Comparator.comparing(NaturalSort::extractNumericalParts).thenComparing(Comparator.naturalOrder()));
		return strings;
	}

	private static List<String> extractNumericParts(String str) {
		List<String> numericParts = new ArrayList<>();
		Pattern pattern = Pattern.compile("\\d+");
		Matcher matcher = pattern.matcher(str);

		while (matcher.find()) {
			numericParts.add(matcher.group());
		}

		return numericParts;
	}
}
```