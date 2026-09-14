# Threads e Closures `move`

`thread::spawn` exige closure cujos dados capturados possam viver além do stack frame, frequentemente com `move` transferindo ownership para thread. `JoinHandle` representa execução e permite join.

```rust
use std::thread;

let data = vec![1, 2, 3];

let handle = thread::spawn(move || {
    println!("{data:?}");
});

handle.join().unwrap();
```

Thread detached pode sobreviver ao estado ao redor, então prefira ownership/join explícitos. Panic em child thread aparece via `join`; defina como aplicação propaga/isola falha.
