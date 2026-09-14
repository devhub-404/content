# Documentación y Doctests

Rustdoc transforma documentation comments en docs navegables y puede compilar/ejecutar ejemplos fenced como doctests. Esto mantiene los examples cerca de la API y verifica que sigan compilando.

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

Documenta contracts, ownership, errors, panics, safety requirements y uso real. Los doctests complementan unit/integration tests y son especialmente útiles en libraries públicas.
