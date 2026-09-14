# Namespaces e Diretivas `using`

Namespaces organizam nomes de tipos e evitam colisões entre libraries. File-scoped namespaces deixam a declaração concisa, enquanto `using` importa namespaces, cria aliases ou traz membros static ao scope. Isso afeta lookup de nomes, não instalação de packages.

```csharp
namespace Billing;

using System.Text.Json;

public sealed class InvoiceService
{
    public string Serialize(object value) =>
        JsonSerializer.Serialize(value);
}
```

Escolha namespaces que representem boundaries estáveis do produto em vez de copiar toda pasta mecanicamente. Global usings reduzem repetição, mas devem ficar restritos a dependências realmente onipresentes.
