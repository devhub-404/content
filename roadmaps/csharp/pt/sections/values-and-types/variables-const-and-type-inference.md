# Variáveis, `const` e Inferência de Tipo

Variáveis locais podem usar tipo explícito ou `var`, que pede ao compilador para inferir um tipo estático a partir do initializer. `var` não é dynamic typing. `const` representa constantes de compile time com regras restritas.

```csharp
var message = "hello";
int count = 3;
const int MaxRetries = 5;

message = message.ToUpperInvariant();
```

Use `var` quando o tipo é óbvio ou verboso sem acrescentar significado. Prefira tipo explícito quando ele comunica unidade, abstração ou conversão importante. Use `static readonly` para valores que só podem ser conhecidos em runtime.
