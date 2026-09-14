# Unsafe Rust y Safety Invariants

Unsafe Rust habilita operaciones que el compiler no puede demostrar seguras, como dereference de raw pointers, unsafe functions, mutable statics, unsafe traits y ciertas union operations. No desactiva el borrow checker globalmente.

```rust
unsafe fn read_raw(ptr: *const i32) -> i32 {
    // SAFETY: caller guarantees ptr is valid and aligned.
    unsafe { *ptr }
}
```

Todo unsafe block necesita una safety invariant precisa. Mantén las regiones pequeñas, envuélvelas en abstracciones safe y documenta por qué cada operación es válida. El compiler confía en ese contrato, así que un bug unsafe puede romper assumptions del código safe.
