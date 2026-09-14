# Raw Pointers y Memoria Manual

Los raw pointers `*const T`/`*mut T` pueden ser null, dangling, unaligned o aliased; crearlos suele ser safe, pero hacer dereference es unsafe porque el compiler no puede demostrar las condiciones de memoria.

```rust
let mut value = 42_i32;

let ptr: *mut i32 = &mut value;

unsafe {
    *ptr += 1;
}
```

Usa raw pointers principalmente en FFI, allocators/data structures low-level auditadas. Convertir una reference safe en raw pointer no prolonga el lifetime ni permite romper aliasing rules.
