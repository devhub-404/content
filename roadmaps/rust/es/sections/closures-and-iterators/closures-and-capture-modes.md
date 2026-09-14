# Closures y Modos de Capture

Las closures capturan variables por shared borrow, mutable borrow o move según el body. El compiler infiere el modo mínimo salvo `move`, que fuerza capture por valor/ownership del binding.

```rust
let prefix = String::from("user:");

let label = |id: u64| {
    format!("{prefix}{id}")
};

println!("{}", label(42));
```

El capture mode afecta los traits `Fn`, `FnMut`, `FnOnce`. Las closures long-lived/cross-thread suelen usar `move`, pero mover una reference mueve solo la reference, no transfiere mágicamente el ownership de los datos referenciados.
