# Operator Overloading

C++ lets user-defined types participate in operator syntax when an overload is declared. Operators cannot invent new precedence or arity; they should preserve the conventional meaning readers expect from the operator whenever possible.

```cpp
struct distance {
    double meters;
};

distance operator+(distance a, distance b) {
    return {a.meters + b.meters};
}
```

Overloading arithmetic or comparison can make value types natural to use, while surprising overloads such as using `+` for an unrelated side effect make code harder to understand. C++20's three-way comparison facilities can reduce boilerplate for ordered value types when their semantics fit.
