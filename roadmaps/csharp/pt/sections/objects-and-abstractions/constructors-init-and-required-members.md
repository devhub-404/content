# Constructors, `init` e Required Members

Constructors estabelecem estado inicial válido. Accessors `init` permitem assignment durante inicialização, mas não depois, enquanto `required` diz ao caller que o member precisa receber valor na construção ou initializer.

```csharp
public sealed class User
{
    public required string Name { get; init; }
    public string? Email { get; init; }
}

var user = new User { Name = "Mina" };
```

Use constructors para invariantes que precisam validação imediata e required/init para objetos de dados onde inicialização nomeada é mais clara. `required` não substitui validação de runtime.
