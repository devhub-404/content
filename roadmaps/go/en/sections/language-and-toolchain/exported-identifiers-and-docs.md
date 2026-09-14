# Exported Identifiers and Documentation

Go uses capitalization for package visibility: an identifier beginning with an uppercase Unicode letter is exported from its package. This makes the public API visible directly in source rather than through a separate access modifier system.

```go
package geometry

// Point represents a location in 2D space.
type Point struct {
    X float64
    Y float64
}
```

Documentation comments on exported declarations are part of normal Go API design and are surfaced by `go doc` and pkg.go.dev. Write comments that explain the contract, not merely repeat the identifier name. Unexport implementation details by keeping their names lowercase.
