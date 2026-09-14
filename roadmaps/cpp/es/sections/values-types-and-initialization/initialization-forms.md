# Formas de Inicialización

C++ tiene varias sintaxis de inicialización con reglas distintas de overload resolution y narrowing. La inicialización con braces es útil porque rechaza muchas conversiones narrowing y también inicializa aggregates y tipos compatibles con `std::initializer_list`.

```cpp
int a = 10;
int b(20);
int c{30};

std::vector<int> values{1, 2, 3};
```

No supongas que braces y paréntesis siempre significan lo mismo: la selección de constructor puede cambiar si participan initializer-list constructors. Usa un estilo consistente y comprende la API, especialmente en containers donde `{10, 20}` puede significar dos elementos y no size/value.
