# Slice Copying and Aliasing

Assigning a slice copies only the slice descriptor, not the underlying elements, so both slices may alias the same backing array. The built-in `copy` copies elements into an existing destination slice and handles overlapping slices correctly.

```go
src := []int{1, 2, 3}
dst := make([]int, len(src))

copy(dst, src)
dst[0] = 99
```

Make a real element copy when independent mutation is required. For common cases, `append([]T(nil), src...)` or newer standard-library helpers can also produce copies. Understand whether an API receives shared mutable storage or an independent value.
