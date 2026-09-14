# NuGet y Package References

NuGet es el ecosistema estándar de packages .NET. Los package references declaran dependencies en el project file, restore resuelve el grafo transitivo y opciones de lock/central management mejoran reproducibilidad.

```xml
<ItemGroup>
  <PackageReference
      Include="Example.Library"
      Version="4.2.0" />
</ItemGroup>
```

Trata upgrades como cambios de código: revisa release notes, transitivas, seguridad y compatibilidad. Las libraries públicas deberían mantener pequeña su dependency surface porque las decisiones de package pueden afectar la resolución del consumer.
