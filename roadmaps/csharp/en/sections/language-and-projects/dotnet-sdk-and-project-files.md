# .NET SDK and Project Files

The .NET SDK compiles, runs, tests, publishes, and restores C# projects. A `.csproj` file declares the target framework, output type, package references, build properties, and optional language settings. Modern SDK-style project files are intentionally small because many source files and defaults are discovered automatically.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net10.0</TargetFramework>
  </PropertyGroup>
</Project>
```

Learn `dotnet new`, `dotnet run`, `dotnet build`, `dotnet test`, and `dotnet publish` before adding IDE-specific build steps. The target framework matters because language defaults and available runtime APIs are related but not identical concerns.
