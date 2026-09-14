# Versionamento da Linguagem e Compatibilidade

Versões de C# e target frameworks .NET evoluem juntas, mas descrevem coisas diferentes. O SDK normalmente escolhe versão suportada para o target, e features preview exigem toolchain preview.

```xml
<PropertyGroup>
  <TargetFramework>net10.0</TargetFramework>
  <LangVersion>14.0</LangVersion>
</PropertyGroup>
```

Para libraries, defina mínimos realmente suportados. Evite `LangVersion=latest` em builds compartilhados quando reprodutibilidade importa, pois um SDK futuro pode mudar a sintaxe aceita.
