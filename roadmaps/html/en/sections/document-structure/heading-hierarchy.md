# Heading Hierarchy in Real Documents

A document's headings should form a readable hierarchy from `h1` through `h6`. You do not need to use every level in every page, but the level should reflect nesting. A heading introduces the content that follows until a heading of the same or higher level changes the context.

```html
<h1>Developer handbook</h1>

<section>
  <h2>Frontend</h2>
  <section>
    <h3>Accessibility</h3>
    <h4>Keyboard support</h4>
  </section>
</section>
```

Avoid picking levels from appearance. A tiny `h2` can be styled with CSS, while an `h5` used only because it looks small creates a misleading hierarchy. Screen-reader users often navigate by heading list, so a clean sequence is practical navigation. Multiple `h1` elements are syntactically allowed in modern HTML, but a clear page-level `h1` is still the simplest and most interoperable authoring pattern for ordinary documents.
