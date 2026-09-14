# Dynamic Routes y `getStaticPaths`

Los filenames con brackets crean dynamic route params. En static output, `getStaticPaths` indica qué combinations prerenderizar y puede adjuntar props. En on-demand rendering, los params de la request están disponibles en runtime.

```astro
---
export function getStaticPaths() {
  return [
    { params: { slug: "hello" }, props: { title: "Hello" } },
    { params: { slug: "astro" }, props: { title: "Astro" } }
  ];
}

const { slug } = Astro.params;
const { title } = Astro.props;
---
<h1>{title}</h1>
<p>{slug}</p>
```

Genera solo routes que realmente existan y retorna not-found adecuado para valores desconocidos. Los sitios grandes deben derivar paths de content collections/source of truth en vez de duplicar slugs en routing code.
