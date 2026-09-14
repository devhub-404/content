# Documentation and Doctests

Rustdoc turns documentation comments into browsable API documentation and can compile/run fenced examples as doctests. This keeps important usage examples close to the API and verifies that they continue to compile.

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

Write docs around contracts, ownership, errors, panics, safety requirements, and examples a caller actually needs. Doctests complement unit/integration tests; they are especially valuable for public libraries because they test the exact syntax users see in the documentation.
