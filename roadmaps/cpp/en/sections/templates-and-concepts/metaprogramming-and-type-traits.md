# Type Traits and Compile-time Metaprogramming

`<type_traits>` exposes compile-time information and transformations for types. Type traits, `if constexpr`, constexpr functions, concepts, and template specialization together provide a rich compile-time programming toolkit.

```cpp
#include <type_traits>

template <typename T>
constexpr bool is_small_integer =
    std::is_integral_v<T> && sizeof(T) <= 4;

static_assert(is_small_integer<int>);
```

Use metaprogramming to improve type safety or generate efficient generic code, not to demonstrate cleverness. If the same rule can be expressed as an ordinary constexpr function or concept, that is often easier to read and produces better diagnostics than deeply nested type machinery.
