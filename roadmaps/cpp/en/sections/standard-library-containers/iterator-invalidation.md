# Iterator and Reference Invalidation

Standard containers define when insertions, erasures, rehashing, or reallocation invalidate iterators, pointers, and references. These rules differ significantly between vector-like, node-based, and unordered containers.

```cpp
std::vector<int> values{1, 2, 3};
auto it = values.begin();

values.push_back(4);
// 'it' may now be invalid if reallocation occurred.
```

Using an invalidated iterator is undefined behavior. Before storing long-lived iterators or references, understand which operations the owner may perform. In many designs, storing a stable key or index and looking up again is safer than retaining an iterator across mutations.
