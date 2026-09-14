# Tipos Definidos y Aliases

Una type definition crea un nuevo tipo nombrado con underlying type, por lo que `UserID` y `string` son distintos para assignment y method sets. Sirve para semántica de dominio y para añadir métodos.

```go
type UserID string
type HandlerFunc = func(Request) Response

var id UserID = "u-42"
```

Un type alias con `=` es otro nombre para el mismo tipo y sirve sobre todo para evolución de APIs, código generado o bridges. Usa tipo definido para semántica distinta y alias cuando la identidad deba permanecer igual.
