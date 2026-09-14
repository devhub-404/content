# Analyzers, Formatting y Warnings de Nullability

Los Roslyn analyzers inspeccionan source/semántica durante build e IDE, mientras `.editorconfig` centraliza formatting y style. Nullable analysis es una de las herramientas de corrección más valiosas en C# moderno.

```xml
<PropertyGroup>
  <Nullable>enable</Nullable>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
</PropertyGroup>
```

Adopta warnings deliberadamente y mantén CI consistente. Suprime solo cuando el código demuestre un hecho que el analyzer no puede ver y documenta suppressions no obvias.
