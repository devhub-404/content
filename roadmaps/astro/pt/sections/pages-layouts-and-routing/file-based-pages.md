# Pages por File-based Routing

Arquivos em `src/pages` viram routes conforme path. Pages podem ser `.astro`, Markdown, MDX com integration, HTML ou endpoint files. Uma page é responsável pelo document retornado naquela URL.

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

Use links `<a href>` normais porque Astro gera web documents comuns. Mantenha URL tree intencional/estável; file placement vira behavior público. Extraia page shell repetido para layouts em vez de duplicar HTML, metadata, nav e footer.
