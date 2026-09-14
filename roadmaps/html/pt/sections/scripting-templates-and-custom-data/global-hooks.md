# `id`, `class` e `data-*`

`id` identifica um elemento dentro do documento e deve ser único quando usado como identificador. Ele suporta navegação por fragmento, relações entre label e controle, relações ARIA, scripts e estilização. `class` fornece um ou mais nomes de classe reutilizáveis e é o gancho comum para componentes e utilitários CSS.

```html
<section id="pricing" class="panel featured">
  <button data-product-id="sku-4182">Add to cart</button>
</section>
```

Atributos personalizados iniciados por `data-` armazenam dados específicos da aplicação no elemento e ficam disponíveis ao JavaScript por `dataset`. Use-os para dados que realmente pertencem à aplicação, não para reinventar atributos padrão. IDs, classes e data attributes são ganchos; sozinhos, não fornecem significado semântico ao conteúdo.
