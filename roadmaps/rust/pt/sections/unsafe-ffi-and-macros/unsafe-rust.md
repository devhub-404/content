# Unsafe Rust e Safety Invariants

Unsafe Rust libera operações que compiler não consegue provar seguras, como dereference raw pointers, unsafe functions, mutable statics, unsafe traits e certas union operations. Não desliga borrow checker globalmente.

```rust
unsafe fn read_raw(ptr: *const i32) -> i32 {
    // SAFETY: caller guarantees ptr is valid and aligned.
    unsafe { *ptr }
}
```

Todo unsafe block precisa de safety invariant preciso. Mantenha regiões pequenas, envolva em abstrações safe e documente por que cada operação é válida. Compiler confia nesse contrato, então bug unsafe pode quebrar assumptions do código safe.
