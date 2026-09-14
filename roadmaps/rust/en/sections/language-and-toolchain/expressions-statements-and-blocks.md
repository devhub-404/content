# Expressions, Statements, and Blocks

Rust is expression-oriented. Literals, function calls, `if`, `match`, and blocks can produce values. A block's final expression without a semicolon becomes the block result, while adding a semicolon turns an expression into a statement that evaluates to `()`.

```rust
fn square(x: i32) -> i32 {
    let result = {
        let y = x * x;
        y
    };

    result
}
```

This distinction explains idioms such as returning the final expression without `return`. Use expression-oriented control flow when it clarifies data flow, but do not compress several side effects into one unreadable expression merely because the language allows it.
