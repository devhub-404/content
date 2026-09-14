# Raw Pointers e Memória Manual

Raw pointers `*const T`/`*mut T` podem ser null, dangling, unaligned ou aliased; criá-los geralmente é safe, mas dereference é unsafe porque compiler não prova condições de memória.

```rust
let mut value = 42_i32;

let ptr: *mut i32 = &mut value;

unsafe {
    *ptr += 1;
}
```

Use raw pointers principalmente em FFI, allocators/data structures low-level auditadas. Converter reference safe para raw pointer não prolonga lifetime nem permite quebrar aliasing rules.
