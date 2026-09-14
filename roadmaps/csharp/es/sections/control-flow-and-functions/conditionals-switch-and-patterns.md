# Condicionales, `switch` y Patterns

`if` maneja branching Boolean general, mientras `switch` statements y expressions combinan branching con pattern matching. Los patterns modernos prueban tipos, constantes, relaciones, propiedades, listas, combinaciones lógicas y capturas.

```csharp
string Describe(object value) => value switch
{
    int n when n > 0 => "positive int",
    string { Length: 0 } => "empty string",
    null => "null",
    _ => "other"
};
```

Usa switch expression cuando una entrada mapee claramente a un resultado y statement cuando las ramas tengan un workflow mayor. Los diagnostics de exhaustividad son especialmente útiles con enums y modelos cerrados.
