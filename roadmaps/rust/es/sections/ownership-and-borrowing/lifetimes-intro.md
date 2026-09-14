# Relaciones de Lifetime

Los lifetimes describen relaciones entre references para que el compilador pueda demostrar su validez. La mayoría se infiere mediante elision; las annotations explícitas aparecen cuando varios inputs/outputs tienen relaciones que la inferencia no puede determinar.

```rust
fn longer<'a>(a: &'a str, b: &'a str) -> &'a str {
    if a.len() >= b.len() { a } else { b }
}
```

Una annotation no prolonga el lifetime de un valor; solo declara una relación que el caller debe cumplir. Si los lifetimes se vuelven muy complejos, considera retornar un owned value o reorganizar el almacenamiento.
