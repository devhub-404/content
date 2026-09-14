# `Arc`, `Mutex`, `Send` y `Sync`

`Arc<T>` ofrece shared ownership thread-safe y `Mutex<T>` acceso mutable sincronizado. Los auto traits `Send`/`Sync` codifican seguridad al mover ownership/references entre threads.

```rust
use std::sync::{Arc, Mutex};

let counter = Arc::new(Mutex::new(0));

let shared = Arc::clone(&counter);
let handle = std::thread::spawn(move || {
    *shared.lock().unwrap() += 1;
});

handle.join().unwrap();
```

El compiler rechaza muchos data races, pero deadlocks y logical races siguen siendo posibles. Mantén lock scopes pequeños, define ordering y evita mantener guards durante bloqueos/awaits sin entender las consecuencias.
