# Template Expressions y Directives

Los templates Astro mezclan HTML con JavaScript expressions y directives. Las expressions hacen conditional rendering/map, mientras directives como `class:list`, `set:html`, `is:inline`, `client:*` y `server:*` cambian cómo Astro trata un element/component.

```astro
---
const items = ["HTML", "CSS", "JS"];
const active = true;
---

<ul class:list={["topics", { active }]}>
  {items.map(item => <li>{item}</li>)}
</ul>
```

Las directives tienen semántica de framework; entiende qué cambia cada una. `set:html` puede crear XSS con contenido no confiable y las client/server directives afectan entrega de JavaScript o rendering boundaries, no solo apariencia.
