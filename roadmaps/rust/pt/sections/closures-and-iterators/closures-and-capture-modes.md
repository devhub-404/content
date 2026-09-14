# Closures e Modos de Capture

Closures capturam variáveis por shared borrow, mutable borrow ou move conforme o body. O compiler infere o modo mínimo salvo `move`, que força capture por valor/ownership do binding.

```rust
let prefix = String::from("user:");

let label = |id: u64| {
    format!("{prefix}{id}")
};

println!("{}", label(42));
```

Capture afeta traits `Fn`, `FnMut`, `FnOnce`. Closures long-lived/cross-thread frequentemente usam `move`, mas mover uma reference move só a reference, não transfere magicamente ownership dos dados referenciados.
