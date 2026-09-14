# Performance Budgets e Default Zero-JS

A maior alavanca de performance do Astro é arquitetural: server-render conteúdo sem client state e hidrate só boundaries interativas. Isso reduz download, parse, execution e memory de JavaScript antes de micro-optimization.

```astro
---
import ProductGrid from "../components/ProductGrid.astro";
import CartButton from "../components/CartButton.jsx";
---

<ProductGrid products={products} />
<CartButton client:load />
```

Defina budgets de JS, images, fonts e route latency em condições reais. Island ainda pode enviar bundle grande e static page pode ser lenta por images/third-party scripts. Meça page inteira em vez de assumir que “Astro” automaticamente é rápido.
