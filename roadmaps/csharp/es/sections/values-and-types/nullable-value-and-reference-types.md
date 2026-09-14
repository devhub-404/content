# Tipos Value y Reference Nullable

Los value types usan `T?` para representar valor o null mediante `Nullable<T>`. Los nullable reference types son principalmente análisis del compilador: `string?` describe si null es esperado y habilita warnings ante posibles dereferences.

```csharp
int? count = null;
string? nickname = null;

string display = nickname ?? "anonymous";
int value = count.GetValueOrDefault();
```

Las annotations mejoran contratos, pero no validan datos de runtime. Valida deserialización, base de datos, reflection e interop cuando sea necesario. Prefiere `?`, `??`, pattern matching y guards explícitos frente a esparcir el operador `!` por el código.
