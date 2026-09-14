# Raw Pointers and Manual Memory

Raw pointers `*const T` and `*mut T` can be null, dangling, unaligned, aliased, or otherwise invalid; creating one is generally safe, but dereferencing it is unsafe because the compiler cannot verify the necessary memory conditions.

```rust
let mut value = 42_i32;

let ptr: *mut i32 = &mut value;

unsafe {
    *ptr += 1;
}
```

Use raw pointers primarily at FFI boundaries, custom allocators/data structures, and carefully audited low-level abstractions. Converting a safe reference to a raw pointer does not extend the lifetime of the pointee or permit violating aliasing rules.
