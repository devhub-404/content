# Exceptions Personalizadas y Contratos de Error

Las exceptions personalizadas ayudan cuando callers necesitan distinguir un fallo de dominio sin parsear el mensaje. Deriva de `Exception`, conserva inner exceptions al envolver y da un significado estable al tipo.

```csharp
public sealed class InvalidOrderException : Exception
{
    public InvalidOrderException(string message)
        : base(message) { }
}
```

No toda validación merece custom exception. Try-patterns, result types o colecciones de validación pueden ser mejores cuando el fallo es flujo esperado. Las exceptions funcionan mejor cuando la llamada no puede producir normalmente su resultado prometido.
