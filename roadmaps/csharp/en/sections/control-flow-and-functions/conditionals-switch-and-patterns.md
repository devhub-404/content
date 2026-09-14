# Conditionals, `switch`, and Patterns

`if` handles general Boolean branching, while `switch` statements and switch expressions combine branching with pattern matching. Modern patterns can test types, constants, relational conditions, properties, lists, logical combinations, and variable capture.

```csharp
string Describe(object value) => value switch
{
    int n when n > 0 => "positive int",
    string { Length: 0 } => "empty string",
    null => "null",
    _ => "other"
};
```

Use a switch expression when one input cleanly maps to one result, and a statement when branches need larger imperative workflows. Exhaustiveness diagnostics become especially useful with enums and closed domain models.
