# `std::expected` and Error Values

C++23 `std::expected<T, E>` represents either a successful value or an error value in the return type. It is useful when failure is part of the ordinary domain flow and callers should handle it explicitly without exceptions.

```cpp
std::expected<config, parse_error>
parse_config(std::string_view input) {
    // ...
}
```

Choose an error type that carries actionable context and compose expected-returning operations consistently. Do not wrap every impossible programming bug in `expected`; assertions, preconditions, exceptions, or termination can be more appropriate depending on the contract.
