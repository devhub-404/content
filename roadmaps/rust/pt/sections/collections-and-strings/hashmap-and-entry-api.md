# `HashMap` e Entry API

`HashMap<K,V>` armazena key/value por hashing e possui ambos. Keys precisam equality/hash compatíveis, e lookup pode usar borrowed key forms quando traits permitem.

```rust
use std::collections::HashMap;

let mut counts = HashMap::new();

for word in ["rust", "go", "rust"] {
    *counts.entry(word).or_insert(0) += 1;
}
```

Entry API combina lookup e insertion/update sem hash duplicado, ideal para counters/caches. Ordem de iteração não é sorted estável. Se ordem faz parte do contrato, use estrutura ordered ou ordene keys explicitamente.
