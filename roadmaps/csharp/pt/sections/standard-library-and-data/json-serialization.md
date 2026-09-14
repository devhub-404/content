# Serialização JSON

`System.Text.Json` serializa valores .NET para/de JSON usando metadata pública, converters, naming policies e source generation opcional. Desserializar com sucesso não prova que regras de domínio foram satisfeitas.

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};

string json = JsonSerializer.Serialize(user, options);
User? copy = JsonSerializer.Deserialize<User>(json, options);
```

Defina transport models deliberadamente para opcionais, enums, nomes, datas, números e compatibilidade. Valide payload externo após parsing e use source generation quando performance/trimming/AOT importarem.
