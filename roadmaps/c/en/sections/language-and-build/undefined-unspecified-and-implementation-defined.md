# Undefined, Unspecified, and Implementation-defined Behavior

The C standard deliberately leaves some behavior undefined, unspecified, or implementation-defined. Undefined behavior imposes no requirements after the invalid operation, so a compiler may optimize under the assumption that it never occurs. Signed integer overflow, invalid pointer dereferences, and many out-of-bounds accesses are important examples.

```c
#include <limits.h>

int add_one(int x) {
    if (x == INT_MAX) {
        /* handle overflow deliberately */
        return x;
    }
    return x + 1;
}
```

Implementation-defined behavior must be documented by the implementation, while unspecified behavior permits one of several valid outcomes without requiring documentation of which is chosen. Portable C avoids depending on undefined behavior and isolates platform assumptions behind checked interfaces or configuration.
