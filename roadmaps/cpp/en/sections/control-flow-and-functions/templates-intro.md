# Function Templates

A function template describes a family of functions parameterized by types, values, or other templates. When called, template argument deduction determines a specialization that satisfies the call. This is compile-time generic programming, not runtime dynamic dispatch.

```cpp
template <typename T>
T max_value(T a, T b) {
    return b < a ? a : b;
}

auto best = max_value(10, 20);
```

Templates are most useful when the implementation genuinely works for a set of types with a shared syntactic/semantic capability. If the valid operations need to be part of the public contract, concepts make those requirements much clearer than relying on substitution failures deep inside an implementation.
