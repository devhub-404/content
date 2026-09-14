# Standard Algorithms

The standard library provides algorithms for searching, sorting, transforming, partitioning, numeric operations, set operations, and more. They operate through iterators or ranges and separate the algorithm from the container representation.

```cpp
std::sort(values.begin(), values.end());

auto it = std::find(values.begin(), values.end(), target);

std::transform(
    values.begin(),
    values.end(),
    output.begin(),
    [](int x) { return x * 2; }
);
```

Prefer a named algorithm when it states intent better than a loop. Check each algorithm's iterator-category, ordering, complexity, and precondition requirements. Some algorithms reorder elements or invalidate assumptions even when the container itself does not reallocate.
