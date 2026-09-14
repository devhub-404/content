# Namespaces y Directivas `using`

Los namespaces organizan nombres de tipos y evitan colisiones entre libraries. Los file-scoped namespaces hacen concisa la declaración, mientras `using` importa namespaces, crea aliases o trae miembros static al scope. Esto afecta la resolución de nombres, no la instalación de packages.

```csharp
namespace Billing;

using System.Text.Json;

public sealed class InvoiceService
{
    public string Serialize(object value) =>
        JsonSerializer.Serialize(value);
}
```

Elige namespaces que representen boundaries estables del producto en vez de reflejar cada carpeta mecánicamente. Los global usings reducen repetición, pero deben limitarse a dependencias realmente omnipresentes.
