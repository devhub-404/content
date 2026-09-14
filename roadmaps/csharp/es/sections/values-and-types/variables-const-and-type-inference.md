# Variables, `const` e Inferencia de Tipo

Las variables locales pueden usar tipo explícito o `var`, que pide al compilador inferir un tipo estático desde el initializer. `var` no es dynamic typing. `const` representa constantes de compile time con reglas restringidas.

```csharp
var message = "hello";
int count = 3;
const int MaxRetries = 5;

message = message.ToUpperInvariant();
```

Usa `var` cuando el tipo sea obvio o verboso sin aportar significado. Prefiere un tipo explícito cuando comunique una unidad, abstracción o conversión importante. Usa `static readonly` para valores que solo se conocen en runtime.
