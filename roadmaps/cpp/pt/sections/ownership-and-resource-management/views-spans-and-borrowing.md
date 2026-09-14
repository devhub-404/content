# `std::span`, `std::string_view` e Views Borrowed

`std::span` é view não-owning de sequência contígua e `std::string_view` de dados de caracteres. Eles encapsulam pointer-plus-length sem alocar nem possuir o storage subjacente.

```cpp
void print_values(std::span<const int> values) {
    for (int value : values) {
        std::cout << value << '
';
    }
}

void log(std::string_view message);
```

A segurança depende do lifetime: os dados origem precisam viver mais que a view. Nunca retorne view para temporário/local que será destruído. Views são ótimos tipos de borrow em APIs quando ownership permanece em outro lugar.
