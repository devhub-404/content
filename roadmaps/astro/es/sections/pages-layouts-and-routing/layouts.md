# Layouts

Un layout es un Astro component normal usado como estructura reutilizable de page. Suele contener document shell, metadata, navigation y un slot para contenido, pero también puede ser wrapper parcial y anidarse.

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

Mantén responsabilidades amplias/estables, como site chrome o article framing. Los datos específicos quedan en la page salvo verdadero uso compartido. Como un layout es un component normal, recibe typed props y compone otros components normalmente.
