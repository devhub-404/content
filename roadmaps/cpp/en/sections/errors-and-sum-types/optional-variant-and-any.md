# `optional`, `variant`, and `any`

`std::optional<T>` models a value that may be absent. `std::variant<Ts...>` models exactly one active alternative from a known set and supports visitation. `std::any` stores one runtime type without a compile-time closed set.

```cpp
std::optional<user> find_user(id value);

using result = std::variant<success, error>;

std::any metadata = std::string{"tag"};
```

Use the most specific abstraction that represents the domain. Optional is better than a sentinel value, variant is better than `any` when alternatives are known, and `any` is best reserved for genuinely open heterogeneous extension points where runtime type checking is acceptable.
