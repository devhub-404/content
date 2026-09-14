# `noexcept` and Exception Safety

`noexcept` is part of a function's exception specification and states that escaping exceptions are not permitted; if one escapes, the program terminates. Standard containers use noexcept properties of move operations when deciding whether they can move elements during reallocation.

```cpp
class buffer {
public:
    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

Exception safety is usually discussed as no-throw, strong, or basic guarantees. Design operations so invariants survive failure and resources remain owned. Prefer transactional update patterns where the old state remains intact until the new state has been successfully prepared.
