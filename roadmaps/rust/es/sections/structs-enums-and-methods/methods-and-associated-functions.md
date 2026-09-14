# Methods y Associated Functions

Un bloque `impl` define methods y associated functions. Los methods usan receiver como `&self`, `&mut self` o `self`, haciendo explícito borrowing/ownership. Associated functions como `new` no reciben `self`.

```rust
impl User {
    fn new(id: u64, name: impl Into<String>) -> Self {
        Self {
            id,
            name: name.into(),
        }
    }

    fn name(&self) -> &str {
        &self.name
    }
}
```

Elige el receiver según la operación: `&self` observa, `&mut self` muta y `self` consume. Los constructors son convenciones; usa nombres como `new`, `with_capacity` o factories de dominio que comuniquen lo que se crea.
