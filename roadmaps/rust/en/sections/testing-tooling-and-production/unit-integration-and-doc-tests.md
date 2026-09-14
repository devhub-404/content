# Unit, Integration, and Documentation Tests

Unit tests commonly live beside implementation in `#[cfg(test)]` modules, integration tests live under `tests/` and use the crate as an external consumer would, and documentation examples can become doctests. These layers test different visibility and API boundaries.

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

Prefer behavior-focused assertions over mirroring implementation details. Use `Result`-returning tests when `?` improves setup, `#[should_panic]` only for deliberate panic contracts, and keep integration fixtures small enough that failures remain diagnostic.
