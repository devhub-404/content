# Performance and Zero-cost Abstractions

C++ is designed so many abstractions can be compiled down without mandatory runtime overhead compared with a hand-written lower-level form. Templates, iterators, RAII wrappers, and value types often enable optimization because their structure is visible to the compiler.

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

Zero-cost does not mean zero compile time, zero code size, or guaranteed fastest machine code. Measure real workloads with optimized builds and profilers. Prefer clear abstractions first, then optimize the bottleneck that measurement identifies rather than preemptively removing safety or readability.
