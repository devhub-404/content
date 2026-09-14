# Language Versioning and Compatibility

C# language versions and .NET target frameworks evolve together but describe different things. The SDK normally chooses a supported language version for the target framework, and preview language features require a preview-capable toolchain.

```xml
<PropertyGroup>
  <TargetFramework>net10.0</TargetFramework>
  <LangVersion>14.0</LangVersion>
</PropertyGroup>
```

For libraries, define the minimum target frameworks and language/toolchain requirements you actually support. Do not set `LangVersion=latest` in shared builds when reproducibility matters; a future SDK can silently change which syntax is accepted.
