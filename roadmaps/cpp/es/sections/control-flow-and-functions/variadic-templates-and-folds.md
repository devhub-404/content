# Variadic Templates y Fold Expressions

Un parameter pack representa cero o más argumentos de template o función. Pack expansion aplica sintaxis sobre los elementos y las fold expressions reducen el pack con un operador binario en un orden definido.

```cpp
template <typename... Ts>
auto sum(Ts... values) {
    return (values + ...);
}

auto total = sum(1, 2, 3, 4);
```

Los variadic templates sustentan tuples, formatting, factories y forwarding, pero los errores pueden volverse difíciles si el pack atraviesa muchas capas. Mantén la operación simple y aplica constraints al template público.
