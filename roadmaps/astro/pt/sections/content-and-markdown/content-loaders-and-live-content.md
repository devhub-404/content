# Content Loaders e Live Content

Content collections não se limitam a Markdown local. Loaders podem buscar files, APIs, CMS e outros backends apresentando uma content layer tipada. Astro moderno também suporta workflows live para conteúdo externo em rendering modes compatíveis.

```astro
const products = defineCollection({
  loader: customApiLoader({ endpoint: process.env.PRODUCTS_URL }),
  schema: productSchema
});
```

Loader deve definir IDs estáveis, validation e refresh. Conteúdo externo continua input não confiável: valide antes de renderizar. Use build-time para data lenta e live/on-demand quando freshness justifica runtime dependency/latency.
