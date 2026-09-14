# Modelo de Iterators

Iterators generalizam posições em sequências e conectam containers a algoritmos genéricos. Diferentes conceitos garantem diferentes operações, de single-pass até random access e contiguidade.

```cpp
auto first = values.begin();
auto last = values.end();

for (; first != last; ++first) {
    process(*first);
}
```

Use algorithms/ranges quando expressarem claramente a operação. Pares de iterator são tradicionalmente half-open `[first, last)`, tornando ranges vazios e composição previsíveis. Nunca dereference o end iterator.
