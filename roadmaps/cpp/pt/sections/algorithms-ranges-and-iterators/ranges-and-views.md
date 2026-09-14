# Ranges e Views

Ranges permitem que algorithms trabalhem diretamente com range objects e adicionam views composables. Views costumam ser adaptadores lazy e leves que descrevem iteração em vez de construir container novo.

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

Views lazy podem referenciar a origem, então lifetime e mutation importam. Pipelines são bons quando cada etapa comunica transformação clara; se debugging ou complexity ficar opaco, materializar um intermediário pode ser mais claro.
