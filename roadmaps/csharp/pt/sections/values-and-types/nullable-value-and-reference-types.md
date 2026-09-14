# Tipos Value e Reference Nullable

Value types usam `T?` para representar valor ou null via `Nullable<T>`. Nullable reference types são principalmente análise do compilador: `string?` descreve se null é esperado e habilita warnings em possíveis dereferences.

```csharp
int? count = null;
string? nickname = null;

string display = nickname ?? "anonymous";
int value = count.GetValueOrDefault();
```

Annotations melhoram contratos, mas não validam runtime data. Valide deserialization, banco, reflection e interop quando necessário. Prefira `?`, `??`, pattern matching e guards explícitos a espalhar o operador `!` pelo código.
