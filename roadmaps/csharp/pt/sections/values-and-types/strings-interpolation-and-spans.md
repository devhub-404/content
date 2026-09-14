# Strings, Interpolação e Valores Textuais

`string` é sequência imutável de code units UTF-16. Interpolated strings combinam expressões e formatação, raw string literals simplificam texto multilinha e `StringBuilder` ajuda na construção mutável repetida. Indexação não equivale necessariamente a caractere percebido pelo usuário.

```csharp
string name = "Mina";
string message = $"Hello, {name}!";
string raw = """
    line one
    line two
    """;

ReadOnlySpan<char> prefix = message.AsSpan(0, 5);
```

Para parsing sensível a performance, `Span<char>` e `ReadOnlySpan<char>` podem visualizar memória sem criar substrings. Use strings comuns por default e introduza spans quando profiling ou contrato de library justificar as restrições extras.
