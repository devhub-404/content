# API Design and Value Semantics

Good C++ APIs use the type system to make valid usage easy: strong value types for domain concepts, `string_view`/`span` for non-owning views, values for ownership transfer when cheap or movable, and references/pointers for explicit borrowing semantics.

```cpp
class user_id {
public:
    explicit user_id(std::uint64_t value)
        : value_(value) {}

    std::uint64_t value() const noexcept {
        return value_;
    }

private:
    std::uint64_t value_;
};
```

Prefer value semantics and RAII over exposed raw resource handles. Avoid boolean-parameter soup, undocumented ownership, and APIs that require callers to remember cleanup steps. A type with a clear invariant often produces simpler client code than a collection of loosely related helper functions.
