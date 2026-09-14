# FFI and C Interoperability

Foreign Function Interface declarations let Rust call code using external ABIs such as C, and Rust functions can also be exported with controlled ABI and symbol naming. FFI types and layouts must match the external contract exactly.

```rust
use std::ffi::c_int;

unsafe extern "C" {
    fn abs(input: c_int) -> c_int;
}

fn absolute(value: i32) -> i32 {
    unsafe { abs(value) }
}
```

Wrap FFI in a small safe Rust layer that converts raw pointers, error codes, ownership, and string encodings into Rust types. `#[repr(C)]` can give structs/enums specific interoperability layout guarantees, but ABI compatibility, allocation ownership, callbacks, and panic boundaries all need explicit design.
