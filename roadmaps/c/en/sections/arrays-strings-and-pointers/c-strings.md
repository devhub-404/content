# Null-terminated Byte Strings

An ordinary C string is a sequence of nonzero `char` bytes terminated by a zero byte. The terminator is part of the required storage but not the logical string length. Standard string functions assume valid termination and sufficient destination capacity according to each function's contract.

```c
#include <string.h>

char name[32] = "Mina";
size_t length = strlen(name);

if (length + 1 < sizeof name) {
    strcat(name, "!");
}
```

String handling is a major source of memory bugs because a pointer alone does not carry capacity. Prefer APIs and internal abstractions that keep buffer size and used length explicit, check arithmetic for overflow, and avoid unbounded copying or concatenation.
