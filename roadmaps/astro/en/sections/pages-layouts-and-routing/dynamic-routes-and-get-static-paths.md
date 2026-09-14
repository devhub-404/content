# Dynamic Routes and `getStaticPaths`

Bracketed page filenames create dynamic route parameters. In static output, `getStaticPaths` tells Astro which parameter combinations to prerender and can attach props to each generated page. In on-demand rendering, the current request parameters are available at runtime instead.

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

Generate only routes that should actually exist and return a proper not-found result for unknown dynamic values. Large content sites should derive paths from content collections or a source of truth rather than duplicating slugs in routing code.
