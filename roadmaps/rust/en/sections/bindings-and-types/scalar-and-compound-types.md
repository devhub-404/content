# Scalar and Compound Types

Rust's basic scalar types include signed and unsigned integers with explicit widths, `isize`/`usize`, floating-point types, `bool`, and Unicode scalar-value `char`. Compound built-in types include tuples and fixed-size arrays.

```rust
let age: u32 = 42;
let ratio: f64 = 0.75;
let ready: bool = true;
let letter: char = '🦀';

let pair: (i32, &str) = (7, "days");
let values: [i32; 3] = [1, 2, 3];
```

Choose integer widths from the interface and range you need. `usize` is the natural index/size type. Arithmetic overflow behavior depends on operation and build/checking context, so use checked, wrapping, saturating, or overflowing operations when the domain requires a specific policy.
