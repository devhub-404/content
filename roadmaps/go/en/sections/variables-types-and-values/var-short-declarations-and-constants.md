# `var`, Short Declarations, and Constants

`var` declares variables explicitly and can rely on type inference from an initializer. Inside functions, `:=` is the short declaration form and declares at least one new variable in the current scope. Constants are compile-time values with special representability and untyped-constant rules.

```go
var host string = "example.com"
port := 443

const timeoutSeconds = 30
const Pi = 3.141592653589793
```

Use short declarations for local values when the type is obvious, but be alert to shadowing in nested scopes. Constants can be untyped until context gives them a concrete type, which makes numeric constants flexible without forcing an early machine representation.
