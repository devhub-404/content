# Server Islands

Server island adia rendering de server component dinâmico para o resto da page poder ser gerado/cacheado independentemente. Page chega com fallback enquanto conteúdo personalizado ou lento é obtido e inserido separadamente.

```astro
---
import PersonalizedAvatar from "../components/PersonalizedAvatar.astro";
---

<PersonalizedAvatar server:defer>
  <div slot="fallback" class="avatar-placeholder"></div>
</PersonalizedAvatar>
```

Use para regiões isoladas como account UI, inventory ou recommendations. Não divida tudo: cada island cria outra request/render boundary. Escolha onde caching ou latency independente realmente melhora a page.
