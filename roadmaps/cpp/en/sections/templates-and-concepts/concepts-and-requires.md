# Concepts and `requires`

Concepts give names to template requirements and constrain which arguments make a template viable. `requires` clauses and requires-expressions can describe valid operations, nested type requirements, conversions, and combinations of other concepts.

```cpp
#include <concepts>

template <typename T>
concept numeric = std::integral<T> || std::floating_point<T>;

template <numeric T>
T twice(T value) {
    return value + value;
}
```

Constraints improve overload selection, documentation, and diagnostics by moving requirements to the interface. A concept should model a meaningful semantic capability, not merely a list of expressions that happen to compile for current callers.
