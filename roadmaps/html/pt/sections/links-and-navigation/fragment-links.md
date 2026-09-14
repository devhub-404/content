# Links de Fragmento e IDs

Um fragmento de URL iniciado por `#` aponta para um elemento cujo `id` corresponde ao fragmento. Isso permite índices, skip links, deep links e navegação para regiões específicas do documento. IDs usados como destino devem ser únicos dentro do documento.

```html
<a href="#shipping">Jump to shipping</a>

<section id="shipping">
  <h2>Shipping</h2>
  <p>Orders leave within two business days.</p>
</section>
```

Fragmentos fazem parte da URL, então o usuário pode salvar ou compartilhar aquele local específico. Mantenha IDs estáveis quando links externos podem apontar para eles. CSS pode usar `scroll-margin` para impedir que o destino fique escondido sob uma interface sticky, mas a relação de destino em si pertence ao HTML.
