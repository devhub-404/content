# Renderizando Entries de Collections

Queries retornam entries tipadas separando metadata e body. Rendering de entry produz `Content` component-like e dados relacionados conforme formato/pipeline.

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

Mantenha query/sort/filter perto da page ou domain service owner. Collection é content database, não navigation order automático. Torne publication status, dates, locale e URL generation explícitos em vez de depender de filesystem order.
