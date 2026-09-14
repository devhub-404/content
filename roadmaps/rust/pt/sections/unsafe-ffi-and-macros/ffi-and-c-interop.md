# FFI e Interop com C

FFI permite chamar código em ABIs externos como C e exportar functions Rust com ABI/symbol controlados. Types/layouts precisam corresponder exatamente ao contrato externo.

```rust
use std::ffi::c_int;

unsafe extern "C" {
    fn abs(input: c_int) -> c_int;
}

fn absolute(value: i32) -> i32 {
    unsafe { abs(value) }
}
```

Envolva FFI em camada Rust safe pequena que converta raw pointers, error codes, ownership e encodings para tipos Rust. `#[repr(C)]` ajuda layout, mas ABI, allocator ownership, callbacks e panic boundaries exigem design explícito.
