# JSON e Encoding

`encoding/json` mapeia JSON para valores Go usando reflection, fields exportados, tags e regras documentadas. Marshal/unmarshal são convenientes, mas não validam automaticamente regras de domínio.

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

Mantenha transport structs deliberadas, especialmente para opcionais, numbers, unknown fields e timestamps. Para streams, Encoder/Decoder evitam carregar tudo em memória. Dados decoded continuam não confiáveis até validação.
