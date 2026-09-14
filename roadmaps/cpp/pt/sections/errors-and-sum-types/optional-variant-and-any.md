# `optional`, `variant` e `any`

`std::optional<T>` modela valor que pode estar ausente. `std::variant<Ts...>` modela uma alternativa ativa de um conjunto conhecido e suporta visitation. `std::any` armazena um tipo runtime sem conjunto fechado em compile time.

```cpp
std::optional<user> find_user(id value);

using result = std::variant<success, error>;

std::any metadata = std::string{"tag"};
```

Use a abstração mais específica ao domínio. Optional é melhor que sentinel, variant melhor que `any` quando alternativas são conhecidas, e `any` deve ficar para extension points realmente abertos.
