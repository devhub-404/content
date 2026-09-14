# Initialization Forms

C++ has several initialization syntaxes whose overload-resolution and narrowing rules are not identical. Brace initialization is useful because it rejects many narrowing conversions and also initializes aggregates and `std::initializer_list`-aware types.

```cpp
int a = 10;
int b(20);
int c{30};

std::vector<int> values{1, 2, 3};
```

Do not assume every pair of braces means the same thing as parentheses: constructor selection can differ when initializer-list constructors participate. Prefer a consistent style and understand the API being initialized, especially for standard containers where `{10, 20}` may mean two elements rather than a size/value pair.
