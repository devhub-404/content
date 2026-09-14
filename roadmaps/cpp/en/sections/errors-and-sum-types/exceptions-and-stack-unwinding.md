# Exceptions and Stack Unwinding

Exceptions separate error propagation from the normal return path. Throwing searches for a matching handler while stack unwinding destroys automatic objects, which is why RAII is essential for exception-safe resource management.

```cpp
try {
    auto result = parse(input);
    use(result);
} catch (const parse_error &error) {
    std::cerr << error.what() << '
';
}
```

Use exceptions for failures that fit your project's error model and catch where you can recover or add meaningful context. Do not throw from destructors during unwinding. Public APIs should document whether they throw and what invariants remain after failure.
