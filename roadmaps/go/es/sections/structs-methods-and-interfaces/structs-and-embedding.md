# Structs y Embedding

Una struct agrupa fields con nombre en un value type. Las structs se copian por valor salvo que uses pointers. Los fields embedded promueven methods/fields para una selector syntax cómoda, pero embedding es composición, no herencia de clases.

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

Usa nombres de fields en literals cuando quieras robustez frente a cambios de orden. Embedding sirve cuando el tipo realmente forma parte de la abstracción externa; no lo uses solo para imitar inheritance de otro lenguaje.
