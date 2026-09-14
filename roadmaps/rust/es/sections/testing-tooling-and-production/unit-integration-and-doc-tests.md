# Unit, Integration y Documentation Tests

Los unit tests suelen vivir junto a la implementación en módulos `#[cfg(test)]`, los integration tests en `tests/` usan el crate como consumidor externo y los documentation examples pueden convertirse en doctests. Cada capa prueba boundaries distintos.

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

Prefiere assertions de comportamiento frente a reflejar implementación. Los tests pueden retornar `Result` para usar `?`; `#[should_panic]` sirve solo para contratos de panic deliberados. Mantén fixtures diagnósticas.
