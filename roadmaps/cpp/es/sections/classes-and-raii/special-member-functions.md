# Copy, Move y Special Member Functions

C++ puede generar o suprimir constructor por defecto, destructor, copy constructor/assignment y move constructor/assignment según reglas específicas. Estas operaciones determinan cómo los valores copian, transfieren recursos y hacen cleanup.

```cpp
class buffer {
public:
    buffer(const buffer &) = delete;
    buffer &operator=(const buffer &) = delete;

    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

Prefiere la Rule of Zero: compón members como `std::string`, `std::vector` y smart pointers que ya se gestionan. Cuando el tipo posee un recurso low-level único, define o elimina copy/move explícitamente para dejar claro el ownership.
