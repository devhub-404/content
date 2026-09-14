# Nil Interfaces and Typed Nil Values

An interface value conceptually contains a dynamic type and a dynamic value. The interface itself is nil only when both are absent. Storing a typed nil pointer inside an interface produces a non-nil interface value, a common source of surprising checks.

```go
var p *bytes.Buffer = nil
var w io.Writer = p

fmt.Println(w == nil) // false
```

Return a literal nil interface when an error or optional interface result is truly absent. Avoid constructors that wrap typed nil pointers in interfaces unintentionally, and understand the concrete dynamic type when debugging a non-nil interface whose underlying pointer is nil.
