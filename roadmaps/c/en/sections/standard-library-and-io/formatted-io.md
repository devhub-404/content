# Formatted I/O

`printf`-family functions format values according to a format string, and `scanf`-family functions parse formatted input into caller-provided addresses. The format specifiers must match the actual argument types; mismatches in variadic formatted I/O can produce undefined behavior.

```c
#include <stdio.h>

int age = 0;
if (scanf("%d", &age) == 1) {
    printf("age = %d
", age);
}
```

For robust user or file input, line-oriented reading followed by explicit parsing is often easier to validate than a complex `scanf` format. Always check return values. Output formatting also needs correct length modifiers for types such as `size_t` and fixed-width integers.
