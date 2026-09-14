# RTTI and `dynamic_cast`

Runtime Type Information supports operations such as `dynamic_cast` and `typeid` for polymorphic types. `dynamic_cast` can safely test and convert along class hierarchies when a design genuinely needs to inspect the dynamic type.

```cpp
shape &s = get_shape();

if (auto *c = dynamic_cast<circle *>(&s)) {
    std::cout << c->area() << '
';
}
```

Frequent downcasts often indicate that the base interface is missing an operation or that a variant/value-based model would be clearer. Use RTTI for boundaries that truly require type discovery, not as the primary way to dispatch ordinary behavior in an OO hierarchy.
