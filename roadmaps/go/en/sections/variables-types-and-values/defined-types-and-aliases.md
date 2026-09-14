# Defined Types and Type Aliases

A type definition creates a new named type with an underlying type, so `UserID` and `string` are distinct for assignment and method sets. This is useful for domain-specific meaning and attaching methods.

```go
type UserID string
type HandlerFunc = func(Request) Response

var id UserID = "u-42"
```

A type alias with `=` gives another spelling to exactly the same type and is mainly useful for API evolution, generated code, or bridging packages. Choose a defined type when you want distinct domain semantics; choose an alias when identity must remain the same.
