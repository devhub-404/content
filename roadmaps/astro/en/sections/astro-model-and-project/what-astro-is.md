# What Astro Is

Astro is a web framework built around server-first rendering and shipping little or no client JavaScript by default. Astro components render to HTML at build time or on demand, while interactive framework components can be hydrated selectively as islands instead of turning the whole page into a client application.

```astro
---
const title = "Hello Astro";
---
<html>
  <body>
    <h1>{title}</h1>
  </body>
</html>
```

Astro 7.3 is the current release line in September 2026. Learn the HTML-first rendering model before adding React, Vue, or another UI framework. The core question in Astro is not “how do I hydrate everything?” but “which parts actually need browser-side JavaScript?”
