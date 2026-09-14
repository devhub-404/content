# Template Expressions e Directives

Templates Astro misturam HTML com JavaScript expressions e directives. Expressions fazem conditional rendering/map, enquanto directives como `class:list`, `set:html`, `is:inline`, `client:*` e `server:*` alteram como Astro trata element/component.

```astro
---
const items = ["HTML", "CSS", "JS"];
const active = true;
---

<ul class:list={["topics", { active }]}>
  {items.map(item => <li>{item}</li>)}
</ul>
```

Directives têm semântica de framework; entenda o que cada uma muda. `set:html` pode criar XSS com conteúdo não confiável e client/server directives afetam entrega de JavaScript ou rendering boundaries, não apenas aparência.
