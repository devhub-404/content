# Class Templates

Un class template define una familia de tipos parametrizada por tipos o valores. Cada specialization es un tipo propio, como `box<int>` y `box<std::string>`, mientras el source comparte implementación.

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

CTAD puede inferir argumentos desde constructors cuando corresponde, pero tipos explícitos a veces comunican mejor. Mantén pocos template parameters; cada uno añade una dimensión de complejidad de compile time.
