# `std::span`, `std::string_view`, and Borrowed Views

`std::span` is a non-owning view over a contiguous sequence, while `std::string_view` is a non-owning view over character data. They package pointer-plus-length semantics without allocating or owning the underlying storage.

```cpp
void print_values(std::span<const int> values) {
    for (int value : values) {
        std::cout << value << '
';
    }
}

void log(std::string_view message);
```

Their safety depends on lifetime: the source data must outlive the view. Never return a view into a temporary or local object that will be destroyed. Views are excellent borrowing types at API boundaries when ownership remains elsewhere and the lifetime relationship is simple.
