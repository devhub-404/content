# JSON and Encoding

`encoding/json` maps JSON to Go values using reflection, exported fields, tags, and documented conversion rules. Marshaling and unmarshaling are convenient but do not automatically enforce your domain's semantic validation.

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

Keep transport structs deliberate, especially around optional fields, numbers, unknown fields, and timestamps. For streams or multiple JSON values, `json.Encoder` and `json.Decoder` avoid requiring the entire representation in memory. Treat decoded data as untrusted until validated.
