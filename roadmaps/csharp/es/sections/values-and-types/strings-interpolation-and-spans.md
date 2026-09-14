# Strings, Interpolación y Valores Textuales

`string` es una secuencia inmutable de code units UTF-16. Las interpolated strings combinan expresiones y formato, los raw string literals simplifican texto multilínea y `StringBuilder` ayuda en construcción mutable repetida. La indexación no equivale necesariamente a un carácter percibido por el usuario.

```csharp
string name = "Mina";
string message = $"Hello, {name}!";
string raw = """
    line one
    line two
    """;

ReadOnlySpan<char> prefix = message.AsSpan(0, 5);
```

Para parsing sensible a performance, `Span<char>` y `ReadOnlySpan<char>` pueden ver memoria sin crear substrings. Usa strings normales por defecto e introduce spans cuando el profiling o el contrato de la library justifique las restricciones extra.
