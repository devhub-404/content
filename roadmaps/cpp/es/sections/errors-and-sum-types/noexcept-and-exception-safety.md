# `noexcept` y Exception Safety

`noexcept` forma parte de la exception specification y declara que no pueden escapar exceptions; si ocurre, el programa termina. Los containers usan propiedades noexcept de moves para decidir si pueden mover durante reallocation.

```cpp
class buffer {
public:
    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

Exception safety suele describirse como garantías no-throw, strong o basic. Diseña operaciones para conservar invariantes y ownership tras fallos. Los patrones transaccionales ayudan a mantener el estado anterior hasta que el nuevo esté preparado.
