# Declarative Macros

Declarative macros with `macro_rules!` match syntax patterns and expand to Rust syntax before later compilation stages. They can express repetition and syntax that ordinary functions cannot, while remaining hygienic in important name-resolution ways.

```rust
macro_rules! vec_of_strings {
    ($($value:expr),* $(,)?) => {
        vec![$($value.to_string()),*]
    };
}

let names = vec_of_strings!("Ada", "Mina");
```

Use a function or generic when ordinary typed abstraction is sufficient; macros are best when syntax itself needs to vary or repeat. Keep patterns and expansions small enough that compiler errors still lead users back to understandable source code.
