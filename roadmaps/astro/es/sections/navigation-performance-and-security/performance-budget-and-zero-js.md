# Performance Budgets y Default Zero-JS

La mayor palanca de performance de Astro es arquitectónica: server-render contenido sin client state e hidrata solo boundaries interactivas. Esto reduce download, parse, execution y memory de JavaScript antes de micro-optimization.

```astro
---
import ProductGrid from "../components/ProductGrid.astro";
import CartButton from "../components/CartButton.jsx";
---

<ProductGrid products={products} />
<CartButton client:load />
```

Define budgets de JS, images, fonts y route latency bajo condiciones reales. Una island aún puede enviar un bundle grande y una static page puede ser lenta por images/third-party scripts. Mide la page completa en vez de asumir que “Astro” automáticamente es rápido.
