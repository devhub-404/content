# Analyzers, Formatting e Warnings de Nullability

Roslyn analyzers inspecionam source/semântica durante build e IDE, enquanto `.editorconfig` centraliza formatting e style. Nullable analysis é uma das ferramentas de correção mais valiosas em C# moderno.

```xml
<PropertyGroup>
  <Nullable>enable</Nullable>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
</PropertyGroup>
```

Adote warnings deliberadamente e mantenha CI consistente. Suprima apenas quando o código prova fato que analyzer não enxerga e documente suppressions não óbvias.
