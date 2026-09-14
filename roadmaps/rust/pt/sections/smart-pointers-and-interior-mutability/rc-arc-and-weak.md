# `Rc`, `Arc` e `Weak`

`Rc<T>` fornece shared ownership single-thread por reference count; `Arc<T>` oferece versão thread-safe atômica. `Weak<T>` observa sem manter vivo e quebra ownership cycles.

```rust
use std::sync::{Arc, Weak};

let owner = Arc::new(String::from("shared"));
let another = Arc::clone(&owner);
let weak: Weak<String> = Arc::downgrade(&owner);
```

Shared ownership é mais caro e conceitualmente mais fraco que owner único. Use quando domínio realmente tem co-owners. Ciclos strong vazam até serem quebrados; back-references/caches frequentemente devem usar `Weak`.
