# Methods e Associated Functions

Bloco `impl` define methods e associated functions. Methods usam receiver como `&self`, `&mut self` ou `self`, tornando borrowing/ownership explícito. Associated functions como `new` não recebem `self`.

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

Escolha receiver pela operação: `&self` observa, `&mut self` muta e `self` consome. Constructors são convenções; use nomes como `new`, `with_capacity` ou factories de domínio que comuniquem o que é criado.
