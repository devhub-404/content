# `vector`, `array`, and `deque`

`std::vector` is the default dynamic contiguous sequence for many workloads, `std::array` wraps a fixed-size built-in array with container semantics, and `std::deque` provides efficient growth at both ends without requiring one contiguous allocation.

```cpp
std::vector<int> values{1, 2, 3};
values.push_back(4);

std::array<int, 3> fixed{1, 2, 3};

std::deque<int> queue;
queue.push_front(1);
queue.push_back(2);
```

Choose based on operations, invalidation rules, contiguity needs, and size behavior. Vector growth can invalidate references and iterators when it reallocates. Reserve capacity when you know an approximate final size, but do not replace every container choice with premature micro-optimization.
