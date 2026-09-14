# Copy, Move e Special Member Functions

C++ pode gerar ou suprimir constructor default, destructor, copy constructor/assignment e move constructor/assignment conforme regras específicas. Essas operações determinam como valores copiam, transferem recursos e fazem cleanup.

```cpp
class buffer {
public:
    buffer(const buffer &) = delete;
    buffer &operator=(const buffer &) = delete;

    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

Prefira Rule of Zero: componha members como `std::string`, `std::vector` e smart pointers que já se gerenciam. Quando o tipo possui recurso low-level único, defina ou delete copy/move explicitamente para deixar ownership claro.
