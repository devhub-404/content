# Estructura de Component y Frontmatter

Un component `.astro` tiene component script server-side entre `---` y template debajo. Imports, data loading y cálculos en frontmatter se ejecutan durante rendering; ese JavaScript no se envía automáticamente al browser.

```astro
---
import Avatar from "./Avatar.astro";
const { name } = Astro.props;
const greeting = `Hello, ${name}`;
---

<section>
  <Avatar name={name} />
  <p>{greeting}</p>
</section>
```

Usa frontmatter para preparar datos y el template para describir output. Como frontmatter es server/build code, puede acceder a dependencies server-only cuando el rendering lo permita. No uses browser APIs allí salvo que el código se mueva a un client script/island hidratada.
