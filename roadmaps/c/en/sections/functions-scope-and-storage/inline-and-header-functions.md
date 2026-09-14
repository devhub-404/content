# `inline` and Header-defined Functions

The `inline` specifier participates in C's rules for definitions and linkage; it is not a command that forces machine-code inlining. Optimizers may inline functions without the keyword or choose not to inline a function that has it.

```c
static inline int min_int(int a, int b) {
    return a < b ? a : b;
}
```

For small helper functions placed in headers, `static inline` is a common pattern because each translation unit receives an internal-linkage definition. More advanced external-inline patterns have subtle rules and should be used only when the project deliberately needs them.
