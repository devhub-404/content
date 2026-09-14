# RAII y Destructors

RAII liga el lifetime del recurso al lifetime del objeto: adquiere durante construcción/factory y libera en el destructor. La salida normal del scope y el stack unwinding hacen cleanup automáticamente, que es el modelo central de gestión de recursos en C++ idiomático.

```cpp
class file {
public:
    explicit file(const char *path)
        : handle_(std::fopen(path, "r")) {}

    ~file() {
        if (handle_) std::fclose(handle_);
    }

private:
    std::FILE *handle_;
};
```

RAII se aplica a archivos, locks, memoria, sockets, subscriptions y transacciones, no solo al heap. Prefiere wrappers existentes antes de escribir los tuyos. Los destructors normalmente no deben dejar escapar exceptions, especialmente durante unwinding.
