# Variadic Templates and Fold Expressions

A parameter pack represents zero or more template arguments or function arguments. Pack expansion applies syntax across those elements, and fold expressions reduce a pack with a binary operator in a defined association order.

```cpp
template <typename... Ts>
auto sum(Ts... values) {
    return (values + ...);
}

auto total = sum(1, 2, 3, 4);
```

Variadic templates power tuples, formatting libraries, generic factories, and forwarding utilities, but error messages can become difficult when a pack participates in many layers of constraints. Keep the operation on the pack simple and constrain the public template when possible.
