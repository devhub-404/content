# Props e TypeScript

Astro components recebem inputs via `Astro.props`. Interface local `Props` fornece checking para callers e defaults podem usar destructuring normal. Props podem incluir dados, functions usadas no server rendering e valores de components.

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

Trate props como API pública do component. Prefira inputs pequenos de domínio a options object gigante e mantenha server-only values em components server-rendered em vez de passar secrets para components hidratados no browser.
