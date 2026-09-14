# Class Basics and Encapsulation

A class defines a type with data members, member functions, access control, constructors, and other special behavior. `class` defaults to private access while `struct` defaults to public; otherwise both can define the same kinds of members.

```cpp
class account {
public:
    explicit account(std::string owner)
        : owner_(std::move(owner)) {}

    double balance() const {
        return balance_;
    }

private:
    std::string owner_;
    double balance_ = 0.0;
};
```

Encapsulation is useful when the type maintains invariants. Keep state private when callers should not be able to create invalid combinations, and expose operations that preserve the invariant. Avoid writing getters/setters mechanically if they merely recreate a public data struct with extra ceremony.
