# NuGet and Package References

NuGet is the standard package ecosystem for .NET. Package references declare dependencies in project files, restore resolves their transitive graph, and lock/central-management options can make large repositories more reproducible and consistent.

```xml
<ItemGroup>
  <PackageReference
      Include="Example.Library"
      Version="4.2.0" />
</ItemGroup>
```

Treat dependency upgrades like code changes: review release notes, transitive changes, security advisories, and target-framework compatibility. Keep public library dependency surfaces small because package choices can leak into consumer version resolution.
