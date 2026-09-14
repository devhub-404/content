# Threads and `move` Closures

`std::thread::spawn` requires a closure whose captured data can safely outlive the spawning stack frame, which often leads to `move` closures that transfer ownership into the new thread. `JoinHandle` represents the running thread and can be joined for completion.

```rust
use std::thread;

let data = vec![1, 2, 3];

let handle = thread::spawn(move || {
    println!("{data:?}");
});

handle.join().unwrap();
```

A detached thread can outlive surrounding application state, so prefer explicit ownership and joining when possible. Panic in a child thread is reported through `join`; decide how the application should propagate or isolate such failure.
