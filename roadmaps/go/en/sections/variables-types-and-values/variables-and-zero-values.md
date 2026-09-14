# Variables and Zero Values

Every Go variable has a defined zero value when it is declared without an explicit initializer. Numeric values become zero, booleans false, strings empty, and pointers/interfaces/slices/maps/channels/functions have appropriate nil zero states.

```go
var count int
var ready bool
var name string

fmt.Println(count, ready, name)
// 0 false ""
```

Design types so their zero value is useful when practical. Many standard-library types, such as `sync.Mutex` and `bytes.Buffer`, can be used immediately after zero initialization. A useful zero value reduces constructor boilerplate and makes aggregate initialization safer.
