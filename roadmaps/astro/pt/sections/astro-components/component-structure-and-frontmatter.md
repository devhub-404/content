# Estrutura de Component e Frontmatter

Um component `.astro` possui component script server-side entre `---` e template abaixo. Imports, data loading e cálculos no frontmatter executam durante rendering; esse JavaScript não é automaticamente enviado ao browser.

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

Use frontmatter para preparar dados e template para descrever output. Como frontmatter é server/build code, pode acessar dependencies server-only quando rendering permite. Não use browser APIs ali salvo quando código for movido para client script/island hidratada.
