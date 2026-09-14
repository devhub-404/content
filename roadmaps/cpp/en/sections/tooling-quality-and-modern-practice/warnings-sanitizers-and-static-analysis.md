# Warnings, Sanitizers, and Static Analysis

A production C++ build should enable strong warnings and treat unexplained new warnings as defects. Sanitizers expose many memory, UB, and concurrency errors during tests, while static analyzers can reason about suspicious paths that a test suite may not execute.

```cpp
// Example build:
// c++ -std=c++23 -Wall -Wextra -Wconversion //     -fsanitize=address,undefined main.cpp
```

No single tool proves correctness. Use multiple compilers when portability matters, run sanitizers in CI where feasible, and combine them with tests, code review, and dependency analysis. Low-level bugs become much easier to fix when detected close to their origin.
