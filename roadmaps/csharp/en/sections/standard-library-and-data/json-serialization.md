# JSON Serialization

`System.Text.Json` serializes .NET values to and from JSON using public metadata, converters, naming policies, and optional source generation. Serialization is a transport concern; successfully deserializing a type does not prove that all domain rules are satisfied.

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};

string json = JsonSerializer.Serialize(user, options);
User? copy = JsonSerializer.Deserialize<User>(json, options);
```

Define transport models deliberately around optional fields, enum formats, naming, dates, number handling, and version compatibility. Validate external payloads after parsing, and use source generation or tuned options when performance and trimming/AOT compatibility matter.
