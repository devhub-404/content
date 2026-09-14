# Ownership, Moves, and `Copy`

Every Rust value has an owner, and when ownership moves to another binding or function the old binding can no longer use that value unless the type implements `Copy`. This prevents two ordinary owners from independently freeing the same resource.

```rust
let first = String::from("hello");
let second = first;

// println!("{first}"); // moved
println!("{second}");

let a = 10;
let b = a; // i32 implements Copy
println!("{a} {b}");
```

Small plain-value types such as integers commonly implement `Copy`; heap-owning types such as `String` do not. A move is usually a cheap transfer of fields, not a deep copy. When you really need duplicated owned data, call `clone()` deliberately so the cost and semantics are visible.
