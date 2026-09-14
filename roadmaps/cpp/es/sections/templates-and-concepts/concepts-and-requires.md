# Concepts y `requires`

Los concepts dan nombre a requisitos de templates y restringen qué argumentos hacen viable un template. Las `requires` clauses/expressions describen operaciones, tipos anidados, conversiones y combinaciones de concepts.

```cpp
#include <concepts>

template <typename T>
concept numeric = std::integral<T> || std::floating_point<T>;

template <numeric T>
T twice(T value) {
    return value + value;
}
```

Los constraints mejoran overload selection, documentación y diagnostics al mover requisitos a la interfaz. Un concept debe modelar una capacidad semántica útil, no solo una lista de expresiones que compilan hoy.
