# Slots and Component Composition

Slots let a parent provide markup to a reusable Astro component. The default slot handles ordinary children and named slots represent distinct regions such as a header, actions, or sidebar. Fallback content can be provided inside a slot element.

```astro
<!-- Card.astro -->
<article class="card">
  <header><slot name="header" /></header>
  <div><slot /></div>
</article>

<!-- usage -->
<Card>
  <h2 slot="header">Profile</h2>
  <p>Account details</p>
</Card>
```

Use slots when the wrapper should control structure but not the exact nested content. Props are better for data and configuration; slots are better for markup composition. Keep slot names semantic to the component's role rather than tied to incidental CSS positions.
