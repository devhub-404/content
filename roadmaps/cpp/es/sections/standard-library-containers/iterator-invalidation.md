# Invalidation de Iterators y Referencias

Los containers estándar definen cuándo inserciones, borrados, rehash o reallocation invalidan iterators, pointers y references. Las reglas cambian bastante entre containers tipo vector, node-based y unordered.

```cpp
std::vector<int> values{1, 2, 3};
auto it = values.begin();

values.push_back(4);
// 'it' may now be invalid if reallocation occurred.
```

Usar un iterator invalidado es undefined behavior. Antes de guardar iterators/references long-lived, entiende qué mutaciones puede hacer el owner. Muchas veces conservar una clave/índice y volver a buscar es más seguro.
