# Containers Asociativos y Unordered

Los containers asociativos ordenados como `map` y `set` organizan claves mediante una relación de orden, normalmente con garantías tipo árbol. Los unordered containers usan hashing e igualdad.

```cpp
std::map<std::string, int> ordered;
ordered["alice"] = 10;

std::unordered_map<std::string, int> fast;
fast["bob"] = 20;

std::set<int> unique{1, 2, 3};
```

Elige ordered cuando importan recorrido ordenado o queries por rango; unordered cuando basta lookup basado en hash sin orden. La calidad del hash, estabilidad de claves, invalidation y worst-case forman parte del contrato.
