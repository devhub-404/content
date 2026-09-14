# Slots y Component Composition

Los slots permiten que el parent proporcione markup a un component reutilizable. El default slot recibe children y los named slots representan regiones como header, actions o sidebar. Un slot puede tener fallback content.

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

Usa slots cuando el wrapper controla structure pero no el contenido exacto. Props son mejores para data/config; slots para markup composition. Da nombres semánticos ligados al papel del component, no a una posición CSS incidental.
