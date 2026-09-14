# RAII e Destructors

RAII liga lifetime do recurso ao lifetime do objeto: adquira durante construção/factory e libere no destructor. Saída normal de scope e stack unwinding então fazem cleanup automaticamente, o que é o modelo central de resource management em C++ idiomático.

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

RAII vale para arquivos, locks, memória, sockets, subscriptions e transações, não apenas heap. Prefira wrappers existentes antes de criar os próprios. Destructors normalmente não devem deixar exceptions escapar, especialmente durante unwinding.
