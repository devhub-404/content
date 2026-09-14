# Diseño de API y Value Semantics

Las buenas APIs C++ usan el type system para hacer fácil el uso válido: value types fuertes, `string_view`/`span` para views non-owning, valores para transferir ownership cuando son baratos/movibles y references/pointers para borrow explícito.

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

Prefiere value semantics y RAII frente a raw resource handles expuestos. Evita sopa de booleans, ownership no documentado y APIs que exigen cleanup manual. Un tipo con una invariante clara suele simplificar al caller.
