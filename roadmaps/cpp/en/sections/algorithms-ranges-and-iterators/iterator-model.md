# The Iterator Model

Iterators generalize positions in sequences and connect containers to generic algorithms. Different iterator concepts guarantee different operations, from single-pass input iteration to random access and contiguous storage.

```cpp
auto first = values.begin();
auto last = values.end();

for (; first != last; ++first) {
    process(*first);
}
```

Use algorithms and range abstractions instead of hand-written loops when they express the operation clearly. Iterator pairs are traditionally half-open `[first, last)`, which makes empty ranges and range composition predictable. Never dereference the end iterator.
