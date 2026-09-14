# Layouts

Layout é Astro component comum usado como estrutura reutilizável de page. Normalmente contém document shell, metadata, navigation e slot para conteúdo, mas também pode ser wrapper parcial e aninhado.

```astro
---
const { title } = Astro.props;
---
<!doctype html>
<html lang="en">
  <head><title>{title}</title></head>
  <body>
    <SiteHeader />
    <main><slot /></main>
  </body>
</html>
```

Mantenha responsabilidades amplas/estáveis, como site chrome ou article framing. Data específico fica na page salvo compartilhamento real. Como layout é component normal, recebe typed props e compõe outros components normalmente.
