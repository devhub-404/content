# Compiler Warnings and Sanitizers

A serious C build should enable a strong set of compiler warnings and treat new warnings as defects to investigate. Different compilers catch different classes of suspicious code, so portability builds with more than one compiler are valuable.

```c
/* Build example:
   cc -std=c23 -Wall -Wextra -Wconversion       -fsanitize=address,undefined main.c
*/
```

Runtime sanitizers can detect many memory errors, undefined operations, and data races during testing. They do not prove the program is safe on untested paths, but they turn many silent low-level bugs into actionable failures. Combine them with tests and static analysis rather than relying on one tool.
