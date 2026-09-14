# `HashMap` y Entry API

`HashMap<K,V>` almacena key/value mediante hashing y posee ambos. Las keys necesitan equality/hash compatibles y el lookup puede usar borrowed key forms cuando los traits lo permiten.

```rust
use std::collections::HashMap;

let mut counts = HashMap::new();

for word in ["rust", "go", "rust"] {
    *counts.entry(word).or_insert(0) += 1;
}
```

La Entry API combina lookup e insertion/update sin hash duplicado, ideal para counters/caches. El orden de iteración no es sorted estable. Si el orden forma parte del contrato, usa una estructura ordered u ordena keys explícitamente.
