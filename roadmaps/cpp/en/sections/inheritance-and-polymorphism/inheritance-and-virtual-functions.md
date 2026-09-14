# Inheritance and Virtual Functions

Public inheritance models an is-a relationship where a derived object can be used through a base interface. Virtual functions enable runtime dispatch through a base reference or pointer, and `override` asks the compiler to verify that a member really overrides a base virtual function.

```cpp
class shape {
public:
    virtual ~shape() = default;
    virtual double area() const = 0;
};

class circle : public shape {
public:
    explicit circle(double r) : r_(r) {}
    double area() const override { return 3.14159 * r_ * r_; }

private:
    double r_;
};
```

A polymorphic base that will be deleted through a base pointer normally needs a virtual destructor. Prefer inheritance for stable behavioral substitutability, not merely to reuse implementation. Composition is often simpler when one type merely contains or delegates to another.
