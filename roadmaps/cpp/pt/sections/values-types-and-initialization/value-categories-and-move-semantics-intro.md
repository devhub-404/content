# Categorias de Valor e Introdução a Move Semantics

Categorias de expressão como lvalue, xvalue e prvalue influenciam overload resolution, reference binding, materialização e move semantics. Um lvalue normalmente identifica objeto existente, enquanto categorias rvalue costumam representar temporários ou valores expirando.

```cpp
std::string make_name() {
    std::string result = "Mina";
    return result;
}

std::string name = make_name();
std::string other = std::move(name);
```

`std::move` não move nada sozinho; ele faz cast permitindo que overloads de move tratem o objeto como expirando. O objeto moved-from permanece válido conforme contrato do tipo, mas seu valor anterior pode ficar unspecified. Prefira retornar valores naturalmente e deixar copy elision/moves ocorrerem.
