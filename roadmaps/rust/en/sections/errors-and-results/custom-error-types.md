# Custom Error Types

A custom error enum can preserve structured failure categories while carrying context. Implementing `Display` and `std::error::Error` makes the type integrate with standard error chains and tools, while `source()` can expose an underlying cause.

```rust
#[derive(Debug)]
enum ConfigError {
    Io(std::io::Error),
    InvalidSyntax { line: usize },
}
```

Use typed errors when callers benefit from programmatic distinctions. Application top layers may erase heterogeneous errors into a more general reporting type, but lower-level libraries should avoid discarding useful structure solely to make signatures shorter.
