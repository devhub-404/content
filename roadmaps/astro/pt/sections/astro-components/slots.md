# Slots e Component Composition

Slots permitem que parent forneça markup a component reutilizável. Default slot recebe children e named slots representam regiões como header, actions ou sidebar. Slot pode ter fallback content.

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

Use slots quando wrapper controla structure mas não conteúdo exato. Props são melhores para data/config; slots para markup composition. Dê nomes semânticos ligados ao papel do component, não à posição CSS incidental.
