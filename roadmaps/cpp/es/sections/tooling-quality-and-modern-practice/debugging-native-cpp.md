# Depuración de C++ Nativo

Los debuggers nativos inspeccionan stack frames, variables, memoria de objetos, exceptions, threads y core dumps. Compila con símbolos y recuerda que la optimización puede reordenar o eliminar variables, de modo que el debugging optimizado puede diferir del source.

```cpp
std::vector<int> values{1, 2, 3};
std::cout << values.at(10) << '
';
```

Cuando el crash site parece inocente, investiga lifetime errors, iterator invalidation, buffer corruption, data races o moved-from misuse anteriores. Sanitizers y un repro mínimo complementan al debugger. Conserva binario y símbolos exactos de producción.
