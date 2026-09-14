# `Cell` e `RefCell`

Interior mutability permite mutation por shared reference movendo parte das checks para runtime controlado. `Cell<T>` faz replacement/copy-like operations e `RefCell<T>` rastreia borrows dinamicamente.

```rust
use std::cell::RefCell;

let value = RefCell::new(vec![1, 2, 3]);

value.borrow_mut().push(4);

println!("{:?}", value.borrow());
```

Violar regras de `RefCell` causa panic, então não é escape geral. Use em abstrações single-thread quando static borrow checker não expressa o padrão facilmente. Para concorrência, use synchronization types.
