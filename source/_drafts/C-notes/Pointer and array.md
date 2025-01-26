```c
#include <stdio.h>

int main () {
  int arr[] = {100, 101};
}
```

Array is the pointer to the first element of array. With line2, `array+1` can be used to acess next element.
```c
printf("%p | %d\n", arr, *arr);
printf("%p | %d\n", arr, *(arr+1));
```

But array can not be changed, which is different from the pointer.
```c
// arr++;
// The code above will cause a complier error.

int* ptr = arr;
ptr++;
printf("%p | %d\n", ptr, *(ptr));
```
