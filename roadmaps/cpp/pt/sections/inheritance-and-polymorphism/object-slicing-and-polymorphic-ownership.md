# Object Slicing e Ownership Polimórfico

Copiar objeto derivado para objeto base por valor faz slicing e perde a parte derivada. Por isso polimorfismo de runtime normalmente trafega por references ou pointers, não por cópias de Base.

```cpp
std::unique_ptr<shape> make_shape() {
    return std::make_unique<circle>(2.0);
}
```

Para ownership polimórfico, `std::unique_ptr<Base>` é default comum com um owner, enquanto `shared_ptr` só deve aparecer quando lifetime é realmente compartilhado. Virtual destructor e modelo de ownership claro são ambos necessários.
