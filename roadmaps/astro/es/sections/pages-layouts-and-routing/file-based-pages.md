# Pages por File-based Routing

Los archivos en `src/pages` se convierten en routes según su path. Las pages pueden ser `.astro`, Markdown, MDX con integration, HTML o endpoint files. Una page es responsable del document retornado en esa URL.

```astro
// src/pages/about.astro -> /about
---
const title = "About";
---
<html>
  <head><title>{title}</title></head>
  <body><h1>{title}</h1></body>
</html>
```

Usa links `<a href>` normales porque Astro genera web documents normales. Mantén el URL tree intencional/estable; file placement se vuelve behavior público. Extrae page shell repetido a layouts en vez de duplicar HTML, metadata, nav y footer.
