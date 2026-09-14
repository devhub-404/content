# `const`, `volatile`, and `restrict`

`const` prevents modification through a particular lvalue type; it does not necessarily mean the underlying object can never change through another permitted path. `volatile` affects how accesses to volatile objects are treated by the abstract machine and is used for special hardware or signal-related cases, not general thread synchronization.

```c
void scale(size_t n,
           double *restrict out,
           const double *restrict in,
           double factor) {
    for (size_t i = 0; i < n; ++i) {
        out[i] = in[i] * factor;
    }
}
```

`restrict` is an aliasing promise associated with pointer-based accesses, allowing stronger optimization when its requirements are satisfied. Violating a restrict contract can produce undefined behavior. Use qualifiers because they express a real interface contract, not as decoration.
