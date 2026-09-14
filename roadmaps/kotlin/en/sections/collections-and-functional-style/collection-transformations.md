# Collection Transformations

The standard library provides rich transformations such as `map`, `filter`, `associate`, `groupBy`, `partition`, `fold`, `zip`, and sorting functions. Operations on ordinary collections are usually eager and create result collections as needed.

```kotlin
val activeNames = users
    .filter { it.active }
    .map { it.name }
    .sorted()
```

These functions express data transformations clearly, but long chains can allocate intermediate collections. When the dataset is large or the pipeline can short-circuit, a `Sequence` or direct loop may reduce work if measurement shows it matters.
