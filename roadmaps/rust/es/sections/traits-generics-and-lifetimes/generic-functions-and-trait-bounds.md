# Funciones Genéricas y Trait Bounds

Los generics permiten funciones/tipos sobre familias de tipos sin runtime type erasure. Los trait bounds declaran operaciones disponibles y monomorphization suele generar código especializado.

```rust
fn largest<T>(items: &[T]) -> Option<&T>
where
    T: Ord,
{
    items.iter().max()
}
```

Mantén bounds mínimos. Una función que solo necesita ordering no debería exigir clone/display sin necesidad. `where` mejora la lectura con bounds complejos.
