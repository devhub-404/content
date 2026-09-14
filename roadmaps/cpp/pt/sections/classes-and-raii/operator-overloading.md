# Operator Overloading

C++ permite que tipos definidos pelo usuário participem da sintaxe de operadores. Não é possível inventar nova precedência ou aridade e o overload deveria preservar o significado convencional esperado sempre que possível.

```cpp
struct distance {
    double meters;
};

distance operator+(distance a, distance b) {
    return {a.meters + b.meters};
}
```

Overloads de aritmética/comparação tornam value types naturais, enquanto usar `+` para side effect inesperado prejudica leitura. Recursos de three-way comparison do C++20 podem reduzir boilerplate quando a semântica de ordenação é adequada.
