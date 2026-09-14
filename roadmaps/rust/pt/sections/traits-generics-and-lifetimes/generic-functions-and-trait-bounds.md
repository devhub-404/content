# Funções Genéricas e Trait Bounds

Generics permitem funções/tipos sobre famílias de tipos sem runtime type erasure. Trait bounds declaram operações disponíveis e monomorphization normalmente gera código especializado.

```rust
fn largest<T>(items: &[T]) -> Option<&T>
where
    T: Ord,
{
    items.iter().max()
}
```

Mantenha bounds mínimos. Uma função que só precisa de ordering não deve exigir clone/display sem necessidade. `where` melhora leitura com bounds complexos.
