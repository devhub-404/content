# `const`, `constexpr` y Evaluación Constante

`const` impide modificación después de la inicialización a través de esa interfaz, mientras `constexpr` indica que una variable o función puede participar en constant evaluation cuando los inputs lo permiten. C++ moderno puede ejecutar bastante lógica ordinaria durante la compilación.

```cpp
constexpr int square(int x) {
    return x * x;
}

constexpr int area = square(6);
const int runtime_value = read_value();
```

Una función `constexpr` no necesariamente se evalúa en compile time en cada llamada; también puede ejecutarse en runtime. Usa constant evaluation para valores y validaciones naturalmente conocidas durante compilación, no para trasladar trabajo costoso sin un beneficio claro.
