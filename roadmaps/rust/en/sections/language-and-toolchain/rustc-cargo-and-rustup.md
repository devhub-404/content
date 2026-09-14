# `rustc`, Cargo, and Rustup

`rustc` is the compiler, Cargo is Rust's package manager and build tool, and Rustup manages toolchains and components. Most application and library development goes through Cargo rather than invoking `rustc` directly.

```rust
// Typical workflow:
// rustup update stable
// cargo new app
// cargo check
// cargo test
// cargo run
// cargo build --release
```

Use `cargo check` for fast type/lifetime feedback, `cargo test` for tests, `cargo run` while developing binaries, and release builds for realistic optimized performance. Rustup lets projects pin or switch toolchains when reproducibility or nightly-only experiments require it.
