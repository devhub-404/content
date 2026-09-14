# Constructors and Member Initialization

Constructors establish an object's initial invariant. Data members are initialized in declaration order, not in the textual order of the member-initializer list. Prefer direct member initialization over assigning default-constructed members inside the constructor body.

```cpp
class point {
public:
    point(double x, double y)
        : x_(x), y_(y) {}

private:
    double x_;
    double y_;
};
```

Mark single-argument constructors `explicit` when an implicit conversion would be surprising. Default member initializers reduce repetition across constructors. If construction can fail in a recoverable way, consider a factory returning an error-aware result instead of building a half-valid object.
