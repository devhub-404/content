# Class Templates

Class template define família de tipos parametrizada por tipos ou valores. Cada specialization é um tipo próprio, como `box<int>` e `box<std::string>`, enquanto o source compartilha implementação.

```cpp
template <typename T>
class box {
public:
    explicit box(T value)
        : value_(std::move(value)) {}

    const T &get() const { return value_; }

private:
    T value_;
};
```

CTAD pode inferir argumentos a partir de constructors em casos adequados, mas argumentos explícitos às vezes comunicam melhor. Mantenha poucos template parameters; cada um adiciona uma dimensão de complexidade de compile time.
