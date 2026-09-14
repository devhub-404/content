# Performance y Zero-cost Abstractions

C++ está diseñado para que muchas abstracciones se compilen sin overhead runtime obligatorio frente a una forma lower-level escrita a mano. Templates, iterators, wrappers RAII y value types a menudo ayudan a optimizar porque su estructura es visible al compilador.

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

Zero-cost no significa cero compile time, cero tamaño de código ni machine code siempre más rápido. Mide workloads reales con builds optimizados y profiler. Prefiere abstracciones claras y optimiza el bottleneck que indiquen las mediciones.
