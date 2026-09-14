# Filesystem

`std::filesystem` modela paths, directories, status, iteração, cópia e rename com interfaces portáveis. `path` representa um caminho segundo convenções nativas da plataforma, não apenas uma string UTF-8 arbitrária.

```cpp
namespace fs = std::filesystem;

for (const auto &entry :
     fs::directory_iterator(".")) {
    std::cout << entry.path() << '
';
}
```

Operações podem falhar por permissions, races, entries ausentes ou diferenças de plataforma. Há formas throwing e com `std::error_code`. Não assuma que um check garante operação posterior; filesystem pode mudar entre chamadas.
