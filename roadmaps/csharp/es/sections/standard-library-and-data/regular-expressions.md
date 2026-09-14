# Expresiones Regulares

Las regex de .NET ofrecen pattern matching, capture groups, replacements y recursos avanzados. .NET moderno también puede generar implementaciones en compile time para patrones conocidos.

```csharp
var match = Regex.Match(
    "user-42",
    @"^user-(\d+)$");

if (match.Success)
    Console.WriteLine(match.Groups[1].Value);
```

Regex es excelente para patrones léxicos, pero no para todo lenguaje estructurado. Mantén patterns legibles, limita matches costosos no confiables con timeout cuando corresponda y usa string methods cuando la regla sea simple.
