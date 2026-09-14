# `Deref` y `Drop`

`Drop` ejecuta cleanup determinista al salir del scope, haciendo central el RAII. `Deref`/`DerefMut` permiten que tipos smart-pointer-like expongan un target y participen en deref coercions.

```rust
struct Guard {
    name: String,
}

impl Drop for Guard {
    fn drop(&mut self) {
        println!("releasing {}", self.name);
    }
}
```

Implementa `Deref` solo cuando el tipo realmente se comporte como smart pointer. `Drop` debe liberar recursos de forma fiable y no debe depender del process termination. Evita cycles que impidan que owners sean dropped.
