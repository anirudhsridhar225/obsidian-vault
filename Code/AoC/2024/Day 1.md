
# Part 1

decided to do this in C, cuz why not, till i realized C doesn't have hashmaps for part 2

```C
#include <stdio.h>
#include <stdlib.h>  

int compare(const void* num1, const void* num2) {
    return (*(int*)num1 - *(int*)num2);
}  

int compute_difference(int* list1, int* list2, int n) {
    qsort(list1, n, sizeof(int), compare);
    qsort(list2, n, sizeof(int), compare);

    int op = 0;

    for (int i= 0; i < n; i++) {
        op += (abs(list1[i] - list2[i]));
    }

    return op;
}

int main() {

    FILE *file_ptr;
    
    int* list1 = (int*)calloc(1000, sizeof(int));
    int* list2 = (int*)calloc(1000, sizeof(int));
    int n= 0;

    file_ptr = fopen("day1.txt", "r");

    if (NULL == file_ptr) {
        printf("%s\n", "file not found");
        return 0;
    }

    int l1, l2;

    while (fscanf(file_ptr,"%d   %d", &l1, &l2) == 2) {
        list1[n] = l1;
        list2[n] = l2;
        n++;
    }

    fclose(file_ptr);

    int output = compute_difference(list1, list2, n);
    printf("%d\n", output);

    return 0;
}
```


# Part 2

cba to implement my own hashmap in C, so py ftw

```python
def calc(a, b) -> int:
    m1 = {}
    
    for i in range(len(a)):
        if a[i] in m1:
            continue
        else:
            m1[a[i]] = 0

    for i in range(len(b)):
        if b[i] in m1:
            m1[b[i]] += 1
            
    op = 0

    for key in m1.keys():
        op += key * m1[key]

    return op

  
with open("day1.txt", "r") as f:
    lines = f.readlines()

l1 = []
l2 = []
  
for i in lines:
    a, b = map(int, i.split())
    l1.append(a)
    l2.append(b)

result = calc(l1, l2)
print(result)
```
