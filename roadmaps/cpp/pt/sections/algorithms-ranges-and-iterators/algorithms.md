# Algoritmos Padrão

A standard library fornece algoritmos para busca, sorting, transformações, partitions, numéricos e set operations. Eles operam por iterators/ranges e separam o algoritmo da representação do container.

```cpp
std::sort(values.begin(), values.end());

auto it = std::find(values.begin(), values.end(), target);

std::transform(
    values.begin(),
    values.end(),
    output.begin(),
    [](int x) { return x * 2; }
);
```

Prefira algoritmo nomeado quando comunica melhor que um loop. Confira requisitos de iterator category, ordering, complexity e preconditions. Alguns algoritmos reordenam elementos mesmo sem reallocation do container.
