# Conditionals, Loops, and Range-for

C++ has the familiar `if`, `switch`, `for`, `while`, and `do` statements plus range-based `for` for iterable ranges. C++17 and later also allow initializers in `if` and `switch`, which helps keep temporary variables scoped to the decision that uses them.

```cpp
for (const auto &item : items) {
    if (!item.active) {
        continue;
    }
    process(item);
}
```

Use range-for when you need elements rather than indexes, but choose the loop variable carefully: copying `auto item` can be expensive, while `const auto&` borrows each element. Use indexes when position itself matters or you need coordinated access to several sequences.
