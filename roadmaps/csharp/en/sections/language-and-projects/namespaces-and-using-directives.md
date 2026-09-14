# Namespaces and `using` Directives

Namespaces organize type names and avoid collisions across libraries. File-scoped namespace syntax keeps one namespace declaration concise, while `using` directives import namespaces, create aliases, or bring static members into scope. They affect name lookup, not package installation or runtime loading.

```csharp
namespace Billing;

using System.Text.Json;

public sealed class InvoiceService
{
    public string Serialize(object value) =>
        JsonSerializer.Serialize(value);
}
```

Choose namespaces that reflect stable library or product boundaries rather than mirroring every folder mechanically. Global usings can remove repetitive imports, but keep them limited to dependencies that truly belong almost everywhere in the project.
