# `std::expected` e Valores de Erro

C++23 `std::expected<T, E>` representa sucesso ou valor de erro no tipo de retorno. É útil quando falha faz parte do fluxo normal de domínio e callers devem tratá-la explicitamente sem exceptions.

```cpp
std::expected<config, parse_error>
parse_config(std::string_view input) {
    // ...
}
```

Escolha error type com contexto acionável e componha operações expected de forma consistente. Não transforme todo programming bug impossível em `expected`; assertions, preconditions ou exceptions podem ser mais adequadas.
