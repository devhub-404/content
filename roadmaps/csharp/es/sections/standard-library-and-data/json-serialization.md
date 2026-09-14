# Serialización JSON

`System.Text.Json` serializa valores .NET a/desde JSON usando metadata pública, converters, naming policies y source generation opcional. Deserializar con éxito no demuestra que se cumplan las reglas del dominio.

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};

string json = JsonSerializer.Serialize(user, options);
User? copy = JsonSerializer.Deserialize<User>(json, options);
```

Define transport models deliberadamente para opcionales, enums, nombres, fechas, números y compatibilidad. Valida payload externo tras parsing y usa source generation cuando importen performance/trimming/AOT.
