# Specialization y Selección de Overloads

Los templates pueden especializarse explícitamente, parcialmente en contextos como class templates, o competir con overloads ordinarios. Estos mecanismos resuelven problemas distintos e interactúan con deduction/constraints.

```cpp
template <typename T>
void print(const T &value);

template <>
void print<bool>(const bool &value);

void print(const char *value);
```

Prefiere overloads y concepts cuando el comportamiento varía por una capacidad reconocible. La specialization explícita sirve para implementaciones realmente excepcionales, pero puede volverse difícil de descubrir si está dispersa.
