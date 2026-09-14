# Performance e Zero-cost Abstractions

C++ é projetado para que muitas abstrações compilem sem overhead runtime obrigatório comparadas à forma lower-level. Templates, iterators, RAII wrappers e value types frequentemente ajudam otimização porque sua estrutura é visível ao compilador.

```cpp
template <std::ranges::input_range R>
auto total(const R &range) {
    using value_type =
        std::ranges::range_value_t<R>;

    value_type sum{};
    for (const auto &value : range) {
        sum += value;
    }
    return sum;
}
```

Zero-cost não significa zero compile time, zero code size ou machine code sempre mais rápido. Meça workloads reais com build optimized e profiler. Prefira abstrações claras primeiro e otimize o bottleneck medido.
