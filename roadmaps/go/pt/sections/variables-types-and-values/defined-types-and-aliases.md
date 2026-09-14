# Tipos Definidos e Aliases

Uma type definition cria novo tipo nomeado com underlying type, então `UserID` e `string` são distintos para assignment e method sets. É útil para significado de domínio e methods.

```go
type UserID string
type HandlerFunc = func(Request) Response

var id UserID = "u-42"
```

Type alias com `=` é apenas outro nome para o mesmo tipo e serve principalmente a evolução de API, código gerado ou bridges. Use tipo definido para semântica distinta e alias quando identidade precisa permanecer a mesma.
