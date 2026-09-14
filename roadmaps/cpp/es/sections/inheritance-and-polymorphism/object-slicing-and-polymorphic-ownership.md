# Object Slicing y Ownership Polimórfico

Copiar un objeto derivado a un objeto base por valor produce slicing y pierde la parte derivada. Por eso el polimorfismo runtime suele viajar mediante references o pointers, no por copias de Base.

```cpp
std::unique_ptr<shape> make_shape() {
    return std::make_unique<circle>(2.0);
}
```

Para ownership polimórfico, `std::unique_ptr<Base>` es un default común con un único owner, mientras `shared_ptr` debe usarse solo cuando el lifetime es realmente compartido. Se necesitan tanto virtual destructor como un modelo de ownership claro.
