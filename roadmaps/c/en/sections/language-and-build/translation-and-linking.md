# Translation, Compilation, and Linking

A C program is usually split into translation units. The preprocessor handles directives such as `#include`, each source file is translated to object code, and a linker resolves external symbols into an executable or library. Compilation errors, link errors, and runtime failures are different stages and point to different kinds of mistakes.

```c
// math.c
int add(int a, int b) {
    return a + b;
}

// main.c
int add(int, int);

int main(void) {
    return add(2, 3) == 5 ? 0 : 1;
}
```

Declarations let one translation unit describe a symbol defined elsewhere. Definitions allocate storage or provide function bodies. Keep public declarations in headers and include those headers in both the implementation and its users so the compiler checks that declarations stay consistent.
