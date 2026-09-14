# Pattern Matching with `match`

`match` compares a value against patterns and requires exhaustive handling of all possible cases. Patterns can destructure enums, tuples, structs, references, ranges, literals, and nested data, while match guards add extra boolean conditions.

```rust
match status {
    Status::Ready => start(),
    Status::Failed(code) if code >= 500 => retry(),
    Status::Failed(code) => log_error(code),
    Status::Pending => wait(),
}
```

Exhaustiveness turns domain-state changes into compile-time work: adding an enum variant can reveal every match that must be reconsidered. Prefer explicit variants and exhaustive matches over sentinel integers or loosely related booleans when the state space is known.
