# `optional`, `variant` y `any`

`std::optional<T>` modela un valor que puede estar ausente. `std::variant<Ts...>` modela una alternativa activa de un conjunto conocido y soporta visitation. `std::any` almacena un tipo runtime sin conjunto cerrado en compile time.

```cpp
std::optional<user> find_user(id value);

using result = std::variant<success, error>;

std::any metadata = std::string{"tag"};
```

Usa la abstracción más específica para el dominio. Optional es mejor que un sentinel, variant mejor que `any` cuando las alternativas son conocidas y `any` conviene reservarlo para extension points realmente abiertos.
