# Destructuring and Pattern Bindings

Patterns are used beyond `match`: `let`, function parameters in supported forms, `for`, and conditional pattern constructs can destructure values. `..` ignores unneeded parts, `_` ignores one value, and `@` can bind a matched value while also testing a subpattern.

```rust
struct Point {
    x: i32,
    y: i32,
}

let point = Point { x: 3, y: 4 };
let Point { x, y } = point;

let (first, .., last) = (1, 2, 3, 4);
```

Destructure when it exposes the data you actually need. Avoid enormous nested patterns that duplicate the full domain shape; a small helper method or match at the abstraction boundary can be clearer than carrying implementation structure into every caller.
