# Unit, Integration e Documentation Tests

Unit tests normalmente ficam junto da implementação em `#[cfg(test)]`, integration tests em `tests/` usam crate como consumer externo e documentation examples podem virar doctests. Cada layer testa boundaries diferentes.

```rust
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn adds_values() {
        assert_eq!(add(2, 3), 5);
    }
}
```

Prefira assertions de comportamento a espelhar implementação. Tests podem retornar `Result` para usar `?`; `#[should_panic]` serve apenas a panic contract deliberado. Mantenha fixtures diagnósticas.
