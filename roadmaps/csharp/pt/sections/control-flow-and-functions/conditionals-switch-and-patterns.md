# Condicionais, `switch` e Patterns

`if` trata branching Boolean geral, enquanto `switch` statements e expressions combinam branching com pattern matching. Patterns modernos testam tipos, constantes, relações, propriedades, listas, combinações lógicas e capturas.

```csharp
string Describe(object value) => value switch
{
    int n when n > 0 => "positive int",
    string { Length: 0 } => "empty string",
    null => "null",
    _ => "other"
};
```

Use switch expression quando uma entrada mapeia claramente para um resultado e statement quando branches possuem workflow maior. Diagnostics de exhaustividade são especialmente úteis com enums e modelos fechados.
