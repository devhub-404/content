# Filesystem

`std::filesystem` modela paths, directories, estado, iteración, copia y rename mediante interfaces portables. `path` representa una ruta según las convenciones nativas de la plataforma, no simplemente una string UTF-8 arbitraria.

```cpp
namespace fs = std::filesystem;

for (const auto &entry :
     fs::directory_iterator(".")) {
    std::cout << entry.path() << '
';
}
```

Las operaciones pueden fallar por permisos, races, entradas ausentes o diferencias de plataforma. Hay formas throwing y con `std::error_code`. No supongas que un check garantiza una operación posterior; el filesystem puede cambiar entre llamadas.
