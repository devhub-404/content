# `Rc`, `Arc` y `Weak`

`Rc<T>` ofrece shared ownership single-thread mediante reference count; `Arc<T>` ofrece una versión thread-safe atómica. `Weak<T>` observa sin mantener vivo y rompe ownership cycles.

```rust
use std::sync::{Arc, Weak};

let owner = Arc::new(String::from("shared"));
let another = Arc::clone(&owner);
let weak: Weak<String> = Arc::downgrade(&owner);
```

El shared ownership es más costoso y conceptualmente más débil que un owner único. Úsalo cuando el dominio realmente tenga co-owners. Los ciclos strong filtran hasta romperse; back-references/caches suelen usar `Weak`.
