# `rustfmt`, Clippy, and Compiler Lints

Rustfmt provides the conventional formatter, while Clippy adds a large set of semantic lints beyond the compiler's ordinary warnings. Together they reduce style debates and catch suspicious, inefficient, or non-idiomatic patterns.

```rust
// Typical checks:
// cargo fmt --check
// cargo clippy --all-targets --all-features -- -D warnings
// cargo test
```

Do not accept every lint mechanically without understanding its context, but keep CI policies consistent. Project-specific `allow`, `warn`, and `deny` attributes should document why exceptions exist, especially for unsafe code or API-compatibility constraints.
