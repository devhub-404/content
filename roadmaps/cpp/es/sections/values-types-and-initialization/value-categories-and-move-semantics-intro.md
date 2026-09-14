# Categorías de Valor e Introducción a Move Semantics

Las categorías de expresión como lvalue, xvalue y prvalue influyen en overload resolution, reference binding, materialización y move semantics. Un lvalue suele identificar un objeto existente, mientras las categorías rvalue suelen representar temporales o valores que expiran.

```cpp
std::string make_name() {
    std::string result = "Mina";
    return result;
}

std::string name = make_name();
std::string other = std::move(name);
```

`std::move` no mueve nada por sí mismo; hace un cast que permite a overloads de move tratar el objeto como expiring. El objeto moved-from sigue siendo válido según el contrato de su tipo, aunque su valor anterior pueda quedar unspecified. Prefiere retornar valores de forma natural y deja que copy elision/moves ocurran.
