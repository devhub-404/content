# Move Semantics and Perfect Forwarding

Move semantics lets types transfer resources from expiring objects instead of copying them. Rvalue references participate in move overloads, while forwarding references in deduced template contexts can preserve the caller's value category.

```cpp
template <typename T, typename... Args>
std::unique_ptr<T> make_object(Args&&... args) {
    return std::make_unique<T>(
        std::forward<Args>(args)...
    );
}
```

`std::forward` is for forwarding references inside generic wrappers; `std::move` unconditionally treats an expression as expiring. Perfect forwarding is powerful but should be limited to generic infrastructure. Ordinary application functions are clearer with concrete value/reference ownership semantics.
