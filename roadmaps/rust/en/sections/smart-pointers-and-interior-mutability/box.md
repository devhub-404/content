# `Box<T>`

`Box<T>` owns a value allocated on the heap and has a known pointer-sized representation. It is commonly used for recursive types, large values that should move cheaply by pointer, and trait objects requiring ownership.

```rust
enum List {
    Cons(i32, Box<List>),
    Nil,
}
```

Do not reach for `Box` merely because an object is 'large' without measuring. Rust can move stack values efficiently in many cases. Use `Box` when indirection or stable heap ownership is part of the type's structural requirement.
