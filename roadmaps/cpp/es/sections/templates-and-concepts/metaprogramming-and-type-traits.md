# Type Traits y Metaprogramación

`<type_traits>` expone información y transformaciones de tipos en compile time. Traits, `if constexpr`, constexpr functions, concepts y specialization forman un toolkit potente de metaprogramación.

```cpp
#include <type_traits>

template <typename T>
constexpr bool is_small_integer =
    std::is_integral_v<T> && sizeof(T) <= 4;

static_assert(is_small_integer<int>);
```

Usa metaprogramación para seguridad o generación eficiente, no por cleverness. Si la misma regla cabe en una constexpr function o concept ordinario, suele ser más legible y producir mejores diagnostics que machinery muy anidada.
