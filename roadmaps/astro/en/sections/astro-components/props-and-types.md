# Props and TypeScript

Astro components receive inputs through `Astro.props`. A local `Props` interface gives editor and build-time checking for component callers, while defaults can be applied with ordinary destructuring. Props can include serializable data, functions used during server rendering, and framework-specific component values.

```astro
---
interface Props {
  title: string;
  featured?: boolean;
}

const { title, featured = false } = Astro.props;
---

<article class:list={{ featured }}>
  <h2>{title}</h2>
</article>
```

Treat props as the public API of a reusable component. Prefer small domain-specific inputs over one huge options object, and keep server-only values inside server-rendered components rather than passing secrets into hydrated client components where they may become serialized into browser code.
