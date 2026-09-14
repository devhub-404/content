# `Arc`, `Mutex`, `Send` e `Sync`

`Arc<T>` fornece shared ownership thread-safe e `Mutex<T>` acesso mutável sincronizado. Auto traits `Send`/`Sync` codificam segurança de mover ownership/references entre threads.

```rust
use std::sync::{Arc, Mutex};

let counter = Arc::new(Mutex::new(0));

let shared = Arc::clone(&counter);
let handle = std::thread::spawn(move || {
    *shared.lock().unwrap() += 1;
});

handle.join().unwrap();
```

Compiler rejeita muitos data races, mas deadlocks e logical races continuam possíveis. Mantenha lock scopes pequenos, defina ordering e evite segurar guards através de bloqueios/awaits sem entender consequências.
