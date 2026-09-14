# What C Is

C is a compiled systems programming language with a small core, direct memory access, and a standard library focused on portable low-level programming. It gives programs explicit control over object representation, storage, pointers, and resource lifetimes, which is powerful but leaves more correctness responsibility to the programmer than managed languages do.

```c
#include <stdio.h>

int main(void) {
    puts("Hello, C");
    return 0;
}
```

Modern C should be learned as the current standardized language rather than as a collection of 1970s idioms. C23 is the current revision of the C standard. Existing code spans many older standards, so practical C also requires recognizing which features belong to C89, C99, C11, C17, or C23 and which extensions come from a compiler or operating system.
