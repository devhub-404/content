# `String` and `str`

`String` owns a growable UTF-8 byte buffer, while `str` is the unsized string slice type normally used through `&str`. Neither supports arbitrary integer indexing because a byte offset may land inside a multi-byte UTF-8 code point.

```rust
let mut owned = String::from("Olá");
owned.push_str(", Rust");

let borrowed: &str = &owned;
println!("{borrowed}");
```

Use string methods that respect UTF-8 boundaries and decide whether your domain cares about bytes, Unicode scalar values (`chars()`), or user-perceived grapheme clusters. Prefer `&str` parameters for borrowed text and `String` when ownership or mutation is required.
