# Server Islands

A server island defers rendering of a dynamic server component so the rest of a page can be generated or cached independently. The page can arrive quickly with fallback content while personalized or slower server output is fetched and inserted separately.

```astro
---
import PersonalizedAvatar from "../components/PersonalizedAvatar.astro";
---

<PersonalizedAvatar server:defer>
  <div slot="fallback" class="avatar-placeholder"></div>
</PersonalizedAvatar>
```

Use server islands for isolated dynamic regions such as user-specific account UI, inventory, or expensive recommendations. Do not split every server component automatically: each island creates another request/render boundary. Pick boundaries where independent caching or latency materially improves the page.
