# Expressões Regulares

Regex .NET oferece pattern matching, capture groups, replacements e recursos avançados. .NET moderno também pode gerar implementações em compile time para padrões conhecidos.

```csharp
var match = Regex.Match(
    "user-42",
    @"^user-(\d+)$");

if (match.Success)
    Console.WriteLine(match.Groups[1].Value);
```

Regex é ótima para padrões lexicais, mas não para toda linguagem estruturada. Mantenha patterns legíveis, limite matches caros não confiáveis com timeout quando necessário e use string methods quando a regra é simples.
