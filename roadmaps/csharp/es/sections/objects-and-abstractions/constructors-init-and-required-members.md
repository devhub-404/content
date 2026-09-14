# Constructors, `init` y Required Members

Los constructors establecen un estado inicial válido. Los accessors `init` permiten assignment durante inicialización, pero no después, mientras `required` indica al caller que el member debe recibir un valor durante construcción o initializer.

```csharp
public sealed class User
{
    public required string Name { get; init; }
    public string? Email { get; init; }
}

var user = new User { Name = "Mina" };
```

Usa constructors para invariantes que necesitan validación inmediata y required/init para objetos de datos donde la inicialización nombrada sea más clara. `required` no sustituye validación de runtime.
