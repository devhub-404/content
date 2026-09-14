# Slices

A slice is a borrowed view over a contiguous sequence. `&[T]` views elements and `&str` is a UTF-8 string slice. A slice carries both a pointer and length, so it avoids the raw pointer-plus-count convention common in C APIs.

```rust
fn first_word(text: &str) -> &str {
    text.split_whitespace()
        .next()
        .unwrap_or("")
}

let values = [10, 20, 30, 40];
let middle: &[i32] = &values[1..3];
```

Slices do not own their data and therefore inherit a lifetime relationship with the source. Prefer slice parameters over `&Vec<T>` or `&String` when the function only needs generic sequence/text access, because callers can then pass arrays, vectors, strings, or other compatible sources.
