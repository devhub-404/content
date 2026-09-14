# `panic!` and Unrecoverable Errors

`panic!` represents an unrecoverable failure on the current execution path. Panics can unwind the stack or abort depending on build/runtime configuration, and unwinding runs destructors for live values.

```rust
fn positive(value: i32) -> i32 {
    assert!(value > 0, "value must be positive");
    value
}
```

Use panic for violated internal invariants, impossible states, or tests—not as the ordinary response to bad user input, missing files, network failure, or other recoverable conditions. Library APIs should not surprise callers with routine panics that could have been expressed as `Result`.
