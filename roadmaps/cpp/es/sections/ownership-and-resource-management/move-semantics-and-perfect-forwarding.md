# Move Semantics y Perfect Forwarding

Move semantics permite transferir recursos de objetos que expiran en lugar de copiarlos. Las rvalue references participan en overloads de move, mientras las forwarding references en templates pueden conservar la value category del caller.

```cpp
template <typename T, typename... Args>
std::unique_ptr<T> make_object(Args&&... args) {
    return std::make_unique<T>(
        std::forward<Args>(args)...
    );
}
```

`std::forward` se usa con forwarding references en wrappers genéricos; `std::move` trata incondicionalmente la expresión como expiring. Perfect forwarding es potente, pero conviene limitarlo a infraestructura genérica; las funciones ordinarias son más claras con semántica concreta de valores/references.
