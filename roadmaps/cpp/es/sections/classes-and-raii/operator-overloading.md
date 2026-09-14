# Operator Overloading

C++ permite que tipos definidos por el usuario participen en la sintaxis de operadores. No se puede inventar nueva precedencia o aridad y el overload debería conservar el significado convencional esperado siempre que sea posible.

```cpp
struct distance {
    double meters;
};

distance operator+(distance a, distance b) {
    return {a.meters + b.meters};
}
```

Overloads de aritmética/comparación hacen naturales los value types, mientras usar `+` para un side effect inesperado perjudica la lectura. Las facilidades de three-way comparison de C++20 pueden reducir boilerplate cuando la semántica de orden es adecuada.
