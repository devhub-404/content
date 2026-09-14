# `make`, `new`, and Allocation

`new(T)` allocates zeroed storage for one `T` and returns `*T`. `make` initializes the runtime representation of slices, maps, and channels and returns the value itself rather than a pointer.

```go
values := make([]int, 10)
lookup := make(map[string]int)

ptr := new(int)
*ptr = 42
```

Most Go code does not call either function constantly because composite literals and zero values cover many cases. The compiler decides whether storage lives on the stack or heap through escape analysis; source-level `new` does not directly mean 'heap allocation' in the C sense.
