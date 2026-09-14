# Exceptions e Stack Unwinding

Exceptions separam propagação de erro do retorno normal. Throw procura handler compatível enquanto stack unwinding destrói objetos automáticos, por isso RAII é essencial para exception safety.

```cpp
try {
    auto result = parse(input);
    use(result);
} catch (const parse_error &error) {
    std::cerr << error.what() << '
';
}
```

Use exceptions conforme o modelo de erro do projeto e capture onde consegue recuperar ou adicionar contexto. Não lance de destructor durante unwinding. APIs públicas devem documentar o que pode ser lançado e quais invariantes permanecem.
