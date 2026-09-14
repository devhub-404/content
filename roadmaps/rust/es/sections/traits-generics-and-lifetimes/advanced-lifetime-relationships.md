# Parámetros de Lifetime en Tipos y Traits

Los tipos que almacenan references suelen llevar lifetime parameters que describen su validez. Los trait bounds también pueden involucrar lifetimes, incluidos higher-ranked bounds para comportamiento válido con cualquier borrow apropiado.

```rust
struct Excerpt<'a> {
    text: &'a str,
}

impl<'a> Excerpt<'a> {
    fn text(&self) -> &'a str {
        self.text
    }
}
```

No añadas lifetime parameters mecánicamente. Codifican relaciones reales de borrow y pueden dificultar mover el tipo por la aplicación. Si el objeto conceptualmente posee sus datos, una representación owning puede ser más simple.
