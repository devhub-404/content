# Extension Methods y Extension Members

Los extension methods hacen que métodos static aparezcan como llamadas de instancia cuando coincide el receiver. C# 14 también añade extension blocks para members más ricos. El tipo original no se modifica y los members de instancia normales tienen prioridad.

```csharp
public static class TextExtensions
{
    public static bool IsBlank(this string? value) =>
        string.IsNullOrWhiteSpace(value);
}

if (input.IsBlank())
{
    Console.WriteLine("empty");
}
```

Usa extensions para operaciones cohesionadas sobre tipos que no controlas o para mantener helpers discoverable. Evita buckets gigantes que hagan que todo tipo parezca tener métodos no relacionados.
