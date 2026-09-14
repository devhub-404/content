# Undefined Behavior and the Abstract Machine

C++ defines an abstract machine and permits compilers to optimize as if observable behavior is preserved for well-defined programs. Undefined behavior breaks that contract: the implementation has no obligations after the invalid operation. Signed overflow, use-after-lifetime, invalid pointer dereference, data races, and out-of-bounds access are common examples.

```cpp
#include <limits>

int safe_increment(int x) {
    if (x == std::numeric_limits<int>::max()) {
        return x;
    }
    return x + 1;
}
```

Optimization can make UB appear in surprising ways because the compiler is allowed to assume it never happens. Treat compiler warnings, sanitizers, lifetime rules, and standard-library preconditions as part of normal correctness work rather than as optional debugging extras.
