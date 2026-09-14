# Crates, Packages y Targets

Un package es un proyecto Cargo descrito por `Cargo.toml`. Un crate es una unidad de compilación Rust: binaria o library. Un package puede contener varios binary targets, examples, tests, benches y una library principal.

```rust
// Cargo.toml
[package]
name = "example"
version = "0.1.0"
edition = "2024"

[dependencies]
serde = "1"
```

La distinción importa porque visibility/dependencies operan a nivel crate, mientras versioning/metadata operan a nivel package. Organiza targets alrededor de productos y libraries reales, no solo por comodidad de carpetas.
