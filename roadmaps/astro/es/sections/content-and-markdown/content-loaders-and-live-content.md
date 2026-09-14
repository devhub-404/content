# Content Loaders y Live Content

Las content collections no se limitan a Markdown local. Los loaders pueden obtener files, APIs, CMS y otros backends presentando una content layer tipada. Astro moderno también soporta workflows live para contenido externo en rendering modes compatibles.

```astro
const products = defineCollection({
  loader: customApiLoader({ endpoint: process.env.PRODUCTS_URL }),
  schema: productSchema
});
```

Un loader debe definir IDs estables, validation y refresh. El contenido externo sigue siendo input no confiable: valídalo antes de renderizar. Usa build-time para datos lentos y live/on-demand cuando freshness justifique runtime dependency/latency.
