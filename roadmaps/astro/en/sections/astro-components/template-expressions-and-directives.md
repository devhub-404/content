# Template Expressions and Directives

Astro templates mix HTML with JavaScript expressions and Astro directives. Expressions can conditionally render markup or map arrays, while directives such as `class:list`, `set:html`, `is:inline`, `client:*`, and `server:*` change how Astro handles an element or component.

```astro
---
const items = ["HTML", "CSS", "JS"];
const active = true;
---

<ul class:list={["topics", { active }]}>
  {items.map(item => <li>{item}</li>)}
</ul>
```

Directives are framework semantics, so learn what each one changes instead of treating them as decorative attributes. In particular, `set:html` can create XSS risk with untrusted content, and client/server directives affect JavaScript delivery or rendering boundaries rather than only markup appearance.
