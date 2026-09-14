# JSON y Encoding

`encoding/json` mapea JSON a valores Go usando reflection, fields exportados, tags y reglas documentadas. Marshal/unmarshal son cómodos, pero no validan automáticamente reglas del dominio.

```go
type User struct {
    ID   string `json:"id"`
    Name string `json:"name"`
}

var user User
if err := json.Unmarshal(data, &user); err != nil {
    return err
}
```

Diseña deliberadamente las transport structs, especialmente para opcionales, numbers, unknown fields y timestamps. Para streams, Encoder/Decoder evitan cargar todo en memoria. Los datos decoded siguen sin ser confiables hasta validación.
