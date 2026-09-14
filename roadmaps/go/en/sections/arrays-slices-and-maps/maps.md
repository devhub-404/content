# Maps

A map is a built-in hash-map-like reference type from comparable keys to values. Looking up a missing key returns the value type's zero value; the two-result form also reports whether the key was present.

```go
counts := map[string]int{
    "go": 2,
}

counts["rust"]++

value, ok := counts["missing"]
fmt.Println(value, ok)
```

The zero value of a map is nil and readable but cannot accept assignments until initialized with `make` or a literal. Map iteration order is unspecified. Maps are not safe for unsynchronized concurrent writes, and key comparability is part of the type rules.
