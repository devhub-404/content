# `const`, `constexpr`, and Constant Evaluation

`const` prevents modification through that object interface after initialization, while `constexpr` states that a variable or function can participate in constant evaluation when its inputs allow it. Constant evaluation can execute substantial ordinary C++ during compilation.

```cpp
constexpr int square(int x) {
    return x * x;
}

constexpr int area = square(6);
const int runtime_value = read_value();
```

A `constexpr` function is not necessarily evaluated at compile time on every call; it can also run at runtime. Use constant evaluation for values and validation naturally known at compile time, not to move arbitrary expensive work into compilation without a clear benefit.
