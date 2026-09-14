# Props y TypeScript

Los Astro components reciben inputs mediante `Astro.props`. Una interface local `Props` ofrece checking para callers y los defaults pueden usar destructuring normal. Las props pueden incluir datos, functions usadas en server rendering y valores de components.

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

Trata las props como API pública del component. Prefiere inputs pequeños de dominio frente a un options object enorme y mantén server-only values en components server-rendered en vez de pasar secrets a components hidratados en browser.
