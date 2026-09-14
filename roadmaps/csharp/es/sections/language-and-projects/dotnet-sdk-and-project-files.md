# SDK .NET y Archivos de Proyecto

El SDK .NET compila, ejecuta, prueba, publica y restaura proyectos C#. El archivo `.csproj` declara target framework, tipo de salida, packages y propiedades de build. Los proyectos SDK-style modernos son pequeños porque muchos defaults y archivos se descubren automáticamente.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net10.0</TargetFramework>
  </PropertyGroup>
</Project>
```

Aprende `dotnet new`, `dotnet run`, `dotnet build`, `dotnet test` y `dotnet publish` antes de añadir pasos específicos del IDE. Target framework y versión del lenguaje están relacionados, pero no son lo mismo.
