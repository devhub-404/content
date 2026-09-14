# Debugging Native C Programs

Native debuggers let you set breakpoints, inspect stack frames and memory, step through machine-level execution, and analyze crashes or core dumps. Build with debug information and an optimization level appropriate to the debugging task so source-level state remains understandable.

```c
int divide(int a, int b) {
    return a / b;
}
```

When a crash appears far from the cause, look for earlier memory corruption, use-after-free, or invalid size arithmetic. Reproduce with the smallest input, combine a debugger with sanitizers, and preserve the exact binary and symbols used in production when investigating native crashes.
