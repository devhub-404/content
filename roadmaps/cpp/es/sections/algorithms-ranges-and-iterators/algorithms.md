# Algoritmos Estándar

La standard library ofrece algoritmos para búsqueda, sorting, transformaciones, particiones, numéricos y set operations. Operan mediante iterators/ranges y separan el algoritmo de la representación del container.

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

Prefiere un algoritmo con nombre cuando comunique mejor que un loop. Comprueba requisitos de iterator category, ordering, complexity y preconditions. Algunos algoritmos reordenan elementos aunque el container no realoque.
