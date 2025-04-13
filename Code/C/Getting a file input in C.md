```C
#include <stdio.h>
#include <stdlib.h>

int main() {
	FILE *file_ptr;
	file_ptr = fopen("input.txt", "r");

	//input methods are fgets, fscanf, etc.

	fclose(file_ptr);
}
```
