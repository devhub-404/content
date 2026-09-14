# NuGet e Package References

NuGet é o ecossistema padrão de packages .NET. Package references declaram dependencies no project file, restore resolve o grafo transitivo e opções de lock/central management melhoram reprodutibilidade.

```xml
<ItemGroup>
  <PackageReference
      Include="Example.Library"
      Version="4.2.0" />
</ItemGroup>
```

Trate upgrades como mudanças de código: revise release notes, transitivas, security e compatibilidade. Libraries públicas devem manter dependency surface pequena porque escolhas de package podem afetar resolução do consumer.
