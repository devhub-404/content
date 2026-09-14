# `Cell` y `RefCell`

Interior mutability permite mutation a través de shared reference moviendo parte de los checks a runtime controlado. `Cell<T>` hace replacement/copy-like operations y `RefCell<T>` rastrea borrows dinámicamente.

```rust
use std::cell::RefCell;

let value = RefCell::new(vec![1, 2, 3]);

value.borrow_mut().push(4);

println!("{:?}", value.borrow());
```

Violar las reglas de `RefCell` produce panic, así que no es un escape general. Úsalo en abstracciones single-thread cuando el borrow checker estático no exprese fácilmente el patrón. Para concurrencia, usa synchronization types.
