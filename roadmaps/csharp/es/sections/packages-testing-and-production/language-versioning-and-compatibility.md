# Versionado del Lenguaje y Compatibilidad

Las versiones de C# y los target frameworks .NET evolucionan juntas, pero describen cosas distintas. El SDK normalmente elige una versión soportada para el target y las features preview requieren toolchain preview.

```xml
<PropertyGroup>
  <TargetFramework>net10.0</TargetFramework>
  <LangVersion>14.0</LangVersion>
</PropertyGroup>
```

Para libraries, define los mínimos realmente soportados. Evita `LangVersion=latest` en builds compartidos cuando importe la reproducibilidad, porque un SDK futuro puede cambiar la sintaxis aceptada.
