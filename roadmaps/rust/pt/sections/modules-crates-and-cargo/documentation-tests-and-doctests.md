# Documentação e Doctests

Rustdoc transforma documentation comments em docs navegáveis e pode compilar/executar exemplos fenced como doctests. Isso mantém examples próximos da API e verifica que continuam compilando.

```rust
/// Adds two integers.
///
/// # Examples
///
/// ```
/// assert_eq!(example::add(2, 3), 5);
/// ```
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

Documente contracts, ownership, errors, panics, safety requirements e uso real. Doctests complementam unit/integration tests e são especialmente úteis em libraries públicas.
