# Concepts e `requires`

Concepts dão nomes a requirements de templates e restringem quais argumentos tornam um template viável. `requires` clauses/expressions descrevem operações, tipos aninhados, conversions e combinações de concepts.

```cpp
#include <concepts>

template <typename T>
concept numeric = std::integral<T> || std::floating_point<T>;

template <numeric T>
T twice(T value) {
    return value + value;
}
```

Constraints melhoram overload selection, documentação e diagnostics ao mover requisitos para a interface. Um concept deve modelar capacidade semântica útil, não apenas uma lista de expressões que compila hoje.
