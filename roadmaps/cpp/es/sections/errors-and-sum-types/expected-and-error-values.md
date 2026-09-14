# `std::expected` y Valores de Error

C++23 `std::expected<T, E>` representa éxito o valor de error en el tipo de retorno. Es útil cuando el fallo forma parte del flujo normal del dominio y los callers deben tratarlo explícitamente sin exceptions.

```cpp
std::expected<config, parse_error>
parse_config(std::string_view input) {
    // ...
}
```

Elige un error type con contexto accionable y compón operaciones expected de forma consistente. No conviertas todo programming bug imposible en `expected`; assertions, preconditions o exceptions pueden ser más adecuadas.
