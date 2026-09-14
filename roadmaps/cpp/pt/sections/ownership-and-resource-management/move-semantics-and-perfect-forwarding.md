# Move Semantics e Perfect Forwarding

Move semantics permite transferir recursos de objetos expirando em vez de copiá-los. Rvalue references participam de overloads de move, enquanto forwarding references em templates podem preservar a value category do caller.

```cpp
template <typename T, typename... Args>
std::unique_ptr<T> make_object(Args&&... args) {
    return std::make_unique<T>(
        std::forward<Args>(args)...
    );
}
```

`std::forward` serve a forwarding references em wrappers genéricos; `std::move` trata incondicionalmente a expressão como expiring. Perfect forwarding é poderoso, mas deve ficar em infraestrutura genérica; funções comuns ficam mais claras com semântica concreta de valores/references.
