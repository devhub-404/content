# Strings, String Views, and Formatting

`std::string` owns a dynamically sized character sequence, while `std::string_view` borrows a character range. C++20 `std::format` and related formatting facilities provide type-safe formatting without printf-style variadic mismatches.

```cpp
std::string name = "Mina";
std::string_view view = name;

std::string message =
    std::format("Hello, {}!", view);
```

String views do not own or null-terminate their data as a contract, so APIs receiving them should work from length rather than assume C-string semantics. Use owning strings when the callee must retain text beyond the source lifetime.
