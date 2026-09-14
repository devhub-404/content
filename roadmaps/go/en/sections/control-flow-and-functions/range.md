# `range` over Collections and Iterators

`range` iterates arrays, slices, strings, maps, channels, integers in modern Go, and iterator functions supported by the language version. The values produced depend on the range expression, so string iteration is not the same as byte indexing and map order is deliberately unspecified.

```go
for index, value := range values {
    fmt.Println(index, value)
}

for key, value := range lookup {
    fmt.Println(key, value)
}
```

Know whether the iteration variables are copies or references to underlying data. If you need to mutate slice elements, indexing is often clearer than changing the copied range value. Do not write logic that depends on map iteration order unless you sort keys explicitly.
