# RAII and Destructors

RAII binds resource lifetime to object lifetime: acquire the resource during construction or factory creation and release it in the destructor. Stack unwinding and normal scope exit then clean up automatically, which is the central resource-management model of idiomatic C++.

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

RAII applies to files, locks, memory, sockets, subscriptions, transactions, and other resources—not only heap allocation. Prefer existing standard/library RAII wrappers before writing your own. Destructors should not normally let exceptions escape, especially during stack unwinding.
