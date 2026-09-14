# FFI e Interop con C

FFI permite llamar código con ABIs externos como C y exportar functions Rust con ABI/symbol controlados. Los tipos/layouts deben corresponder exactamente al contrato externo.

```rust
use std::ffi::c_int;

unsafe extern "C" {
    fn abs(input: c_int) -> c_int;
}

fn absolute(value: i32) -> i32 {
    unsafe { abs(value) }
}
```

Envuelve FFI en una pequeña capa safe de Rust que convierta raw pointers, error codes, ownership y encodings a tipos Rust. `#[repr(C)]` ayuda con layout, pero ABI, allocator ownership, callbacks y panic boundaries requieren diseño explícito.
