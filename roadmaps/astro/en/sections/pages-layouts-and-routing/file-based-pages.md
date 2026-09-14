# File-based Pages

Files in `src/pages` become routes according to their path. Astro pages can be `.astro`, Markdown, MDX with the integration, HTML, or endpoint files depending on the route. A page is responsible for the document returned for that URL.

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

Use standard `<a href>` links for navigation because Astro outputs normal web documents. Keep the URL tree intentional and stable; file placement becomes public routing behavior. Extract repeated page shells into layouts rather than duplicating `<html>`, metadata, navigation, and footer markup.
