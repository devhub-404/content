# Specialization and Template Overload Selection

Templates can be explicitly specialized, partially specialized in supported contexts such as class templates, or compete with ordinary overloads through overload resolution. These mechanisms solve different problems and interact with deduction and constraints.

```cpp
template <typename T>
void print(const T &value);

template <>
void print<bool>(const bool &value);

void print(const char *value);
```

Prefer overloads and concepts when behavior varies by a recognizable capability. Explicit specialization is useful for a genuinely exceptional type-specific implementation but can become difficult to discover when spread across files. Keep customization points deliberate and documented.
