# Content Loaders and Live Content

Content collections are not limited to local Markdown. Loaders can source content from files, APIs, CMS systems, or other backends while presenting one typed content layer to the application. Modern Astro also supports live collection workflows for externally hosted content in compatible rendering modes.

```astro
const products = defineCollection({
  loader: customApiLoader({ endpoint: process.env.PRODUCTS_URL }),
  schema: productSchema
});
```

A loader should define stable identifiers, validation, and refresh behavior. External content is still untrusted input: validate it before rendering. Choose build-time content for data that changes slowly and live/on-demand content when freshness justifies the runtime dependency and latency.
