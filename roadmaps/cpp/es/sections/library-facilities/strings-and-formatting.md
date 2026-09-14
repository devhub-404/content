# Strings, String Views y Formatting

`std::string` posee una secuencia dinámica de caracteres, mientras `std::string_view` hace borrow. `std::format` ofrece formatting type-safe sin los mismatches variádicos de printf.

```cpp
std::string name = "Mina";
std::string_view view = name;

std::string message =
    std::format("Hello, {}!", view);
```

String views no poseen los datos ni garantizan null termination como contrato, así que las APIs deben trabajar con length. Usa string owning cuando el callee necesite conservar el texto más allá del lifetime de la fuente.
