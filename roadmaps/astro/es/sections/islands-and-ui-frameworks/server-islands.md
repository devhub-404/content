# Server Islands

Un server island difiere rendering de un server component dinámico para que el resto de la page pueda generarse/cachearse de forma independiente. La page llega con fallback mientras contenido personalizado o lento se obtiene e inserta por separado.

```astro
---
import PersonalizedAvatar from "../components/PersonalizedAvatar.astro";
---

<PersonalizedAvatar server:defer>
  <div slot="fallback" class="avatar-placeholder"></div>
</PersonalizedAvatar>
```

Úsalo para regiones aisladas como account UI, inventory o recommendations. No dividas todo: cada island crea otra request/render boundary. Elige donde caching o latency independiente realmente mejore la page.
