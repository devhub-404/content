# Unsafe Rust and Safety Invariants

Unsafe Rust unlocks operations the compiler cannot prove safe, such as dereferencing raw pointers, calling unsafe functions, accessing mutable statics, implementing unsafe traits, and some union operations. It does not disable the borrow checker or other Rust rules globally.

```rust
unsafe fn read_raw(ptr: *const i32) -> i32 {
    // SAFETY: caller guarantees ptr is valid and aligned.
    unsafe { *ptr }
}
```

Every unsafe block should have a precise safety invariant that safe callers can rely on. Keep unsafe regions small, wrap them in safe abstractions after proving the contract, and document why each operation is valid. The compiler trusts your invariant, so bugs here can violate all assumptions of safe code built on top.
