# Generic Functions and Trait Bounds

Generics let functions and types work over families of types without runtime type erasure. Trait bounds specify which operations are available to generic code, and monomorphization often produces specialized machine code for concrete type arguments.

```rust
fn largest<T>(items: &[T]) -> Option<&T>
where
    T: Ord,
{
    items.iter().max()
}
```

Keep bounds as weak as the implementation requires. A function needing only ordering should not require cloning, display, or ownership properties unrelated to its algorithm. `where` clauses improve readability when several parameters have nontrivial bounds.
