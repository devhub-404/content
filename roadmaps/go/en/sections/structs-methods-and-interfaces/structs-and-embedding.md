# Structs and Embedding

A struct groups named fields into a value type. Struct values copy by value unless pointers are used. Anonymous embedded fields promote selected methods and fields for convenient selector syntax, but embedding is composition, not class inheritance.

```go
type Address struct {
    City string
}

type User struct {
    Name string
    Address
}

u := User{
    Name: "Mina",
    Address: Address{City: "Lisbon"},
}
```

Use explicit field names in literals when code should remain robust to field-order changes. Embedding is useful when the embedded type is genuinely part of the outer abstraction; do not use it just to imitate an inheritance hierarchy from another language.
