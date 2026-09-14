# Dynamic Routes e `getStaticPaths`

Filenames com brackets criam dynamic route params. Em static output, `getStaticPaths` informa combinations a prerenderizar e pode anexar props. Em on-demand rendering, params da request ficam disponíveis em runtime.

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

Gere apenas routes que realmente existem e retorne not-found adequado para valores desconhecidos. Sites grandes devem derivar paths de content collections/source of truth em vez de duplicar slugs no routing code.
