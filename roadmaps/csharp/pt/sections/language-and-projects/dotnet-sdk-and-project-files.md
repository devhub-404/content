# SDK .NET e Arquivos de Projeto

O SDK .NET compila, executa, testa, publica e restaura projetos C#. O arquivo `.csproj` declara target framework, tipo de saída, packages e propriedades de build. Projetos SDK-style modernos são pequenos porque vários defaults e arquivos são descobertos automaticamente.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net10.0</TargetFramework>
  </PropertyGroup>
</Project>
```

Aprenda `dotnet new`, `dotnet run`, `dotnet build`, `dotnet test` e `dotnet publish` antes de adicionar passos específicos de IDE. Target framework e versão da linguagem são relacionados, mas não são a mesma coisa.
