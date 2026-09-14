# Strings, String Views e Formatting

`std::string` possui sequência dinâmica de caracteres, enquanto `std::string_view` faz borrow. `std::format` fornece formatting type-safe sem os mismatches variádicos de printf.

```cpp
std::string name = "Mina";
std::string_view view = name;

std::string message =
    std::format("Hello, {}!", view);
```

String views não possuem os dados nem garantem null termination como contrato, então APIs devem trabalhar com length. Use string owning quando o callee precisa reter o texto além do lifetime da origem.
