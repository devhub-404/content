# `collect`, `fold`, and Short-circuiting Consumers

Consumers turn an iterator into a final result. `collect` can build many target collection types, `sum` and `product` reduce numeric streams, `fold` carries an explicit accumulator, and methods such as `find`, `any`, and `all` stop early when their answer is known.

```rust
let sum: i32 = values.iter().copied().sum();

let parsed: Result<Vec<u32>, _> =
    inputs.iter()
        .map(|text| text.parse::<u32>())
        .collect();
```

The target type can influence how `collect` behaves, including collecting an iterator of `Result<T, E>` into `Result<Vec<T>, E>` and stopping at the first error. Prefer the consumer whose semantics already match the operation rather than using `fold` for everything.
