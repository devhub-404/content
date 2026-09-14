# Type Traits e Metaprogramação

`<type_traits>` expõe informação e transformações de tipos em compile time. Traits, `if constexpr`, constexpr functions, concepts e specialization formam toolkit poderoso de metaprogramação.

```cpp
#include <type_traits>

template <typename T>
constexpr bool is_small_integer =
    std::is_integral_v<T> && sizeof(T) <= 4;

static_assert(is_small_integer<int>);
```

Use metaprogramação para segurança ou geração eficiente, não por cleverness. Se a mesma regra cabe em constexpr function ou concept comum, normalmente fica mais legível e gera diagnostics melhores que machinery profundamente aninhada.
