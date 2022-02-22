Assign the value of existing pointer to a new varriable, whose pointer will be different from the original one.
```c
#include <stdio.h>

typedef struct Book {
  char name[20];
} Book;

int main() {
  Book book = {
    "aaa",
    "What this guy",
    100
  };
  Book* book_ptr = &book;
  // reassign, the pointer will be different
  Book book_1 = *book_ptr;
  printf("%p | %p\n", (&book_1), book_ptr);
  // 0x16b9c73f0 | 0x16b9c741c



  int i = 0;
  int* i_ptr = &i;
  int j = *i_ptr;
  printf("%p | %p\n", (&j), i_ptr);
  // 0x16b9c73cc | 0x16b9c73dc

  return 0;
}
```
It seems that the complier assign a new piece of mermory for the new varriable, so it has a different pointer.
