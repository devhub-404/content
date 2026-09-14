# Loops, Ranges, and Progressions

`for` iterates anything that follows Kotlin iteration conventions, while `while` and `do-while` handle condition-driven repetition. Ranges and progressions provide concise integer and comparable sequences, with `..<` expressing an exclusive upper bound.

```kotlin
for (i in 0..<10) {
    println(i)
}

for (value in values) {
    println(value)
}
```

Prefer direct element iteration when indexes are not needed. Use `indices`, `withIndex`, ranges, or collection operations when position is meaningful. Avoid building a collection solely to obtain a range-like loop.
