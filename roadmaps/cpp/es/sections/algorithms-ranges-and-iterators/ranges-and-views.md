# Ranges y Views

Ranges permiten que algorithms trabajen directamente con range objects y añaden views componibles. Las views suelen ser adaptadores lazy y ligeros que describen iteración en vez de construir un container nuevo.

```cpp
auto even_squares =
    values
    | std::views::filter([](int x) { return x % 2 == 0; })
    | std::views::transform([](int x) { return x * x; });

for (int value : even_squares) {
    std::cout << value << '
';
}
```

Las views lazy pueden referenciar la fuente, así que lifetime y mutation siguen importando. Los pipelines son útiles cuando cada etapa comunica una transformación clara; si debugging o complexity se vuelve opaco, materializar un intermedio puede ser más claro.
