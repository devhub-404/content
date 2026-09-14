# Null Pointers and `nullptr`

A null pointer value represents no object or function. C23 adds the `nullptr` keyword and `nullptr_t`, providing a dedicated null pointer constant instead of relying only on integer constant zero or the `NULL` macro.

```c
int *find_value(int *items, size_t n, int target) {
    for (size_t i = 0; i < n; ++i) {
        if (items[i] == target) return &items[i];
    }
    return nullptr;
}
```

Testing a pointer in a condition is still idiomatic, and dereferencing a null pointer remains invalid. Public APIs should document whether null is a valid optional value or an error. Distinguish a null pointer from an empty array or a valid pointer paired with a zero length.
