# Analyzers, Formatting, and Nullability Warnings

Roslyn analyzers inspect source and semantics during builds and IDE work, while `.editorconfig` centralizes formatting and code-style rules. Nullable analysis is one of the most valuable compiler-assisted correctness tools for modern C# projects.

```xml
<PropertyGroup>
  <Nullable>enable</Nullable>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
</PropertyGroup>
```

Adopt warnings deliberately and keep CI consistent so new diagnostics stay close to the change that introduced them. Suppress a warning only when the code proves a fact the analyzer cannot see, and document non-obvious suppressions.
