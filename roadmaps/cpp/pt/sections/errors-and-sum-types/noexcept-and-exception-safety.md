# `noexcept` e Exception Safety

`noexcept` faz parte da exception specification e diz que exceptions não podem escapar; se escaparem, o programa termina. Containers usam propriedades noexcept de moves para decidir se podem mover durante reallocation.

```cpp
class buffer {
public:
    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

Exception safety costuma ser descrita como no-throw, strong ou basic guarantee. Projete operações para preservar invariantes e ownership após falha. Padrões transacionais ajudam a manter o estado antigo até o novo estar pronto.
