# Functions and Return Types

Function parameter types are explicit, and `-> T` declares a return type. Functions returning nothing explicitly return the unit type `()`. A final expression without a semicolon is commonly used as the return value.

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}

fn log(message: &str) {
    println!("{message}");
}
```

Keep ownership in the signature visible: `String` may move or own data, `&str` borrows text, and `&mut T` borrows mutably. In Rust, function types are not only data-shape contracts; they also describe important lifetime and ownership relationships.
