# Structs e Embedding

Struct agrupa fields nomeados em value type. Structs copiam por valor salvo uso de pointers. Fields embedded promovem methods/fields para selector syntax conveniente, mas embedding é composição, não herança de classes.

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

Use nomes de fields em literals quando quiser robustez a mudanças de ordem. Embedding funciona quando o tipo realmente faz parte da abstração externa; não use apenas para imitar inheritance de outra linguagem.
