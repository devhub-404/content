# Depuração de C++ Nativo

Debuggers nativos inspecionam stack frames, variáveis, memória de objetos, exceptions, threads e core dumps. Compile com símbolos e lembre que otimização pode reordenar/eliminar variáveis, então debugging optimized pode divergir do source.

```cpp
std::vector<int> values{1, 2, 3};
std::cout << values.at(10) << '
';
```

Quando o crash site parece inocente, investigue lifetime errors, iterator invalidation, buffer corruption, data races ou moved-from misuse anteriores. Sanitizers e repro mínimo complementam debugger. Preserve binário e símbolos exatos de produção.
