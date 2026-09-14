# Renderizando Entries de Collections

Las queries retornan entries tipadas separando metadata y body. Renderizar una entry produce un `Content` component-like y datos relacionados según formato/pipeline.

```astro
---
import { getCollection, render } from "astro:content";

const posts = await getCollection("blog");
const post = posts[0];
const { Content } = await render(post);
---

<article>
  <h1>{post.data.title}</h1>
  <Content />
</article>
```

Mantén query/sort/filter cerca de la page o domain service owner. Una collection es una content database, no un navigation order automático. Haz explícitos publication status, dates, locale y URL generation en vez de depender de filesystem order.
