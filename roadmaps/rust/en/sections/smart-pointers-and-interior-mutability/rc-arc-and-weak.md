# `Rc`, `Arc`, and `Weak`

`Rc<T>` provides single-threaded reference-counted shared ownership, while `Arc<T>` provides thread-safe atomic reference counting. `Weak<T>` observes the allocation without keeping the value alive and is used to break ownership cycles.

```rust
use std::sync::{Arc, Weak};

let owner = Arc::new(String::from("shared"));
let another = Arc::clone(&owner);
let weak: Weak<String> = Arc::downgrade(&owner);
```

Shared ownership is more expensive and conceptually weaker than one clear owner. Use it when the domain genuinely has co-owners. Cycles of strong references leak until the cycle is broken; model back-references and caches with `Weak` where appropriate.
