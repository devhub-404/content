# Associative and Unordered Containers

Ordered associative containers such as `map` and `set` organize keys by an ordering relation, commonly with tree-like complexity guarantees. Unordered containers such as `unordered_map` and `unordered_set` use hashing and equality.

```cpp
std::map<std::string, int> ordered;
ordered["alice"] = 10;

std::unordered_map<std::string, int> fast;
fast["bob"] = 20;

std::set<int> unique{1, 2, 3};
```

Choose ordered containers when sorted traversal, ordered queries, or comparator semantics matter; choose unordered containers for hash-based lookup when ordering is unnecessary. Hash quality, key stability, iterator invalidation, and worst-case behavior are part of the contract, not incidental details.
