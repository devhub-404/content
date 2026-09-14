# `Arc`, `Mutex`, `Send`, and `Sync`

`Arc<T>` gives shared thread-safe ownership, while `Mutex<T>` provides synchronized mutable access. The auto traits `Send` and `Sync` encode whether ownership or references can safely cross thread boundaries and are automatically derived for many compositions.

```rust
use std::sync::{Arc, Mutex};

let counter = Arc::new(Mutex::new(0));

let shared = Arc::clone(&counter);
let handle = std::thread::spawn(move || {
    *shared.lock().unwrap() += 1;
});

handle.join().unwrap();
```

The compiler rejects many data-race-prone designs before runtime, but deadlocks and higher-level race conditions remain possible. Keep lock scopes small, define lock ordering, and do not hold synchronous mutex guards across blocking or async suspension points without understanding the consequences.
