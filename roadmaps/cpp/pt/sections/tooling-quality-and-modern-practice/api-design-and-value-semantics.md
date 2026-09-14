# Design de API e Value Semantics

Boas APIs C++ usam o type system para tornar uso válido fácil: value types fortes, `string_view`/`span` para views non-owning, valores para ownership transfer quando barato/movable e references/pointers para borrowing explícito.

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

Prefira value semantics e RAII a raw resource handles expostos. Evite sopa de booleans, ownership não documentado e APIs que exigem cleanup manual. Um tipo com invariante clara costuma simplificar o caller.
