# Threads y Closures `move`

`thread::spawn` exige una closure cuyos datos capturados puedan vivir más que el stack frame, frecuentemente con `move` transfiriendo ownership al thread. `JoinHandle` representa la ejecución y permite join.

```rust
use std::thread;

let data = vec![1, 2, 3];

let handle = thread::spawn(move || {
    println!("{data:?}");
});

handle.join().unwrap();
```

Un thread detached puede vivir más que el estado circundante, así que prefiere ownership/join explícitos. Un panic en child thread aparece mediante `join`; define cómo la aplicación propaga o aísla el fallo.
