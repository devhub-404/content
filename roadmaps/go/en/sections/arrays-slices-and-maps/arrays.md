# Arrays

An array type includes its length: `[3]int` and `[4]int` are different types. Arrays are values, so assignment and parameter passing copy the array unless a pointer is used.

```go
var a [3]int
b := [3]int{10, 20, 30}

fmt.Println(a, b)
```

Arrays are important as the storage underlying slices and for fixed-size domain values, but most variable-length collection APIs use slices. Use arrays when the fixed length itself is meaningful or stack/value semantics are desirable.
