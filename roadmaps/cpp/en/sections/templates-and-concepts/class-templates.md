# Class Templates

A class template defines a family of class types parameterized by types or values. Each specialization is its own type, such as `box<int>` and `box<std::string>`, while the template source expresses their shared implementation.

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

Class template argument deduction can infer template arguments from constructors in suitable cases, but explicit type arguments may still communicate intent more clearly. Keep the template parameter set minimal; every parameter becomes another dimension of compile-time complexity.
