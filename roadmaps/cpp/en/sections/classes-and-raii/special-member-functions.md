# Copy, Move, and Special Member Functions

C++ can generate or suppress default constructor, destructor, copy constructor, copy assignment, move constructor, and move assignment according to special rules. These operations determine how values copy, transfer resources, and clean up.

```cpp
class buffer {
public:
    buffer(const buffer &) = delete;
    buffer &operator=(const buffer &) = delete;

    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

Prefer the Rule of Zero: compose members such as `std::string`, `std::vector`, and smart pointers that already manage themselves, so your class needs no custom special members. When a type owns a unique low-level resource, explicitly define or delete copy/move operations to make ownership behavior unambiguous.
