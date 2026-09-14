# Modelo de Iterators

Los iterators generalizan posiciones en secuencias y conectan containers con algoritmos genéricos. Diferentes conceptos garantizan distintas operaciones, desde single-pass hasta random access y contigüidad.

```cpp
auto first = values.begin();
auto last = values.end();

for (; first != last; ++first) {
    process(*first);
}
```

Usa algorithms/ranges cuando expresen claramente la operación. Los pares de iterators son tradicionalmente half-open `[first, last)`, lo que hace predecibles los rangos vacíos y la composición. Nunca hagas dereference del end iterator.
