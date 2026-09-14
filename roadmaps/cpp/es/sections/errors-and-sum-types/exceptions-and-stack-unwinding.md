# Exceptions y Stack Unwinding

Las exceptions separan propagación de errores del retorno normal. Throw busca un handler compatible mientras stack unwinding destruye objetos automáticos, por eso RAII es esencial para exception safety.

```cpp
try {
    auto result = parse(input);
    use(result);
} catch (const parse_error &error) {
    std::cerr << error.what() << '
';
}
```

Usa exceptions según el modelo de error del proyecto y captura donde puedas recuperar o añadir contexto. No lances desde destructors durante unwinding. Las APIs públicas deben documentar qué pueden lanzar y qué invariantes permanecen.
