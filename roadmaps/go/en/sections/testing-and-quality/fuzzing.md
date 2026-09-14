# Fuzz Testing

Go's testing package includes fuzzing support that mutates seed inputs to discover crashes, invalid assumptions, and edge cases. Fuzz targets are especially valuable for parsers, encoders, protocol handlers, and functions with large input spaces.

```go
func FuzzParse(f *testing.F) {
    f.Add("seed")

    f.Fuzz(func(t *testing.T, input string) {
        _ = Parse(input)
    })
}
```

A useful fuzz target checks invariants rather than merely asserting that the function does not panic. Keep fuzz inputs bounded where necessary, add discovered regressions to the corpus, and combine fuzzing with ordinary deterministic tests for known behavior.
