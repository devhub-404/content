# Editions, MSRV, and Compatibility

An edition selects a coherent set of language defaults and migrations while keeping crates from different editions interoperable. A crate can also declare an MSRV (minimum supported Rust version) with `rust-version`, which is distinct from the edition itself.

```rust
[package]
name = "example"
version = "0.1.0"
edition = "2024"
rust-version = "1.90"
```

Using a new standard-library API, Cargo feature, or language feature can raise the real MSRV even when the edition does not change. Libraries should test their declared MSRV in CI if they promise one, and applications should pin toolchains or dependency lockfiles according to their reproducibility needs.
