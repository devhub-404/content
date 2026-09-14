# `HashMap` and the Entry API

`HashMap<K, V>` stores key/value pairs using hashing. Keys need equality and hashing behavior, and the map owns both keys and values. Lookup can borrow a compatible key form when the relevant traits permit it.

```rust
use std::collections::HashMap;

let mut counts = HashMap::new();

for word in ["rust", "go", "rust"] {
    *counts.entry(word).or_insert(0) += 1;
}
```

The entry API combines lookup and insertion/update without hashing the key twice and is ideal for counters and caches. Iteration order is not a stable sorted order. If ordered traversal is part of the contract, use an ordered structure or sort extracted keys explicitly.
