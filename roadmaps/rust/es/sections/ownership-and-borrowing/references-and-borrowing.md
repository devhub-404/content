# References y Borrowing

Una reference hace borrow de un valor sin tomar ownership. `&T` proporciona acceso read-only y el owner sigue siendo responsable del lifetime. Borrowing permite usar datos sin moves/copies innecesarios.

```rust
fn length(text: &String) -> usize {
    text.len()
}

let name = String::from("Mina");
let size = length(&name);

println!("{name} {size}");
```

El borrow checker garantiza que las references no sobrevivan a los datos y aplica reglas de aliasing. Prefiere parámetros borrowed como `&str` o `&[T]` cuando una función solo necesita observar y no tomar ownership.
