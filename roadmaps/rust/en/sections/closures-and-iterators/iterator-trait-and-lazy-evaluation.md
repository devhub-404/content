# The `Iterator` Trait and Lazy Evaluation

An iterator produces a sequence through repeated `next()` calls and is lazy: adapter methods build a pipeline but do no work until a consuming operation drives the iterator. This separates sequence description from evaluation.

```rust
let values = vec![1, 2, 3, 4];

let doubled: Vec<_> = values
    .iter()
    .map(|value| value * 2)
    .collect();
```

Iterator chains often compile to tight loops without intermediate collections. Use adapters such as `map`, `filter`, `flat_map`, `take`, `zip`, and `enumerate` when they state intent clearly, but a plain `for` loop is better when control flow or side effects dominate.
