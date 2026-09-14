# `if`, `loop`, `while`, and `for`

`if` is an expression and both branches must produce compatible types when its value is used. `loop` repeats indefinitely and can itself produce a value through `break expression`. `while` handles conditional repetition and `for` consumes an iterator.

```rust
let label = if ready { "ready" } else { "waiting" };

for value in values {
    println!("{value}");
}

let result = loop {
    if done() {
        break 42;
    }
};
```

Prefer `for` over manual indexing when you simply need elements. Labels can target outer loops when nested control flow requires it, but deeply nested loops often benefit from extraction into a function with an early return.
