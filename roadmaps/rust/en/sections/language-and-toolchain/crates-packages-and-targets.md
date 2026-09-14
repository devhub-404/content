# Crates, Packages, and Targets

A package is a Cargo project described by `Cargo.toml`. A crate is a Rust compilation unit: either a binary crate or a library crate. One package can contain multiple binary targets, examples, tests, benches, and at most one primary library target.

```rust
// Cargo.toml
[package]
name = "example"
version = "0.1.0"
edition = "2024"

[dependencies]
serde = "1"
```

Keep the distinction clear because compiler errors, visibility, and dependency boundaries operate at crate level, while versioning and dependency metadata operate at package level. Organize targets around actual products and reusable libraries instead of putting unrelated binaries into one accidental crate.
