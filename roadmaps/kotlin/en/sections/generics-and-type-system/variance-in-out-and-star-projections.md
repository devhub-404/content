# Variance: `in`, `out`, and Star Projections

Declaration-site variance lets a generic type state that it only produces (`out`) or consumes (`in`) values of a type parameter, enabling safe subtype relationships. Use-site projections and star projections handle situations where variance cannot be fixed on the declaration.

```kotlin
interface Producer<out T> {
    fun produce(): T
}

interface Consumer<in T> {
    fun consume(value: T)
}
```

Variance should follow the actual API surface. A type that both consumes and produces `T` is normally invariant. Do not add `out` or `in` only to make one assignment compile; check whether all exposed operations really support that relationship.
