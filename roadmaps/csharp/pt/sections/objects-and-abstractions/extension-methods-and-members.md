# Extension Methods e Extension Members

Extension methods fazem static methods aparecerem como chamadas de instância quando o receiver combina. C# 14 também adiciona extension blocks para members mais ricos. O tipo original não é modificado e members de instância normais têm prioridade.

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

Use extensions para operações coesas sobre tipos que você não controla ou para manter helpers discoverable. Evite buckets gigantes que fazem todo tipo parecer possuir métodos sem relação.
