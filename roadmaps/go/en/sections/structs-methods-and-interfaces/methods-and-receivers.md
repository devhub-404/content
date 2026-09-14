# Methods and Receivers

A method is a function declared with a receiver parameter attached to a defined type. Value receivers operate on a copy of the receiver value, while pointer receivers can mutate the original and avoid copying large structs.

```go
type Counter struct {
    value int
}

func (c *Counter) Inc() {
    c.value++
}

func (c Counter) Value() int {
    return c.value
}
```

Choose receiver style consistently for a type. If any important method needs pointer semantics or the type should not be copied, pointer receivers are usually appropriate across the method set. Receivers do not provide automatic null safety: a nil pointer receiver is only valid if the method handles it deliberately.
