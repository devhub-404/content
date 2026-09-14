# Value Categories and Move Semantics

C++ expression value categories such as lvalue, xvalue, and prvalue influence overload resolution, reference binding, object materialization, and move semantics. An lvalue generally identifies an existing object, while rvalue categories often represent temporary or expiring values.

```cpp
std::string make_name() {
    std::string result = "Mina";
    return result;
}

std::string name = make_name();
std::string other = std::move(name);
```

`std::move` does not move anything by itself; it casts an expression so move-aware overloads may treat the object as expiring. The moved-from object remains valid according to its type's contract but its previous value may be unspecified. Prefer returning values naturally and let copy elision or moves occur.
