# Performance Budgets and Zero-JS Defaults

Astro's strongest performance lever is architectural: server-render the content that does not need client state and hydrate only interactive boundaries. This can reduce JavaScript download, parse, execution, and memory cost before any micro-optimization is considered.

```astro
---
import ProductGrid from "../components/ProductGrid.astro";
import CartButton from "../components/CartButton.jsx";
---

<ProductGrid products={products} />
<CartButton client:load />
```

Set budgets for JavaScript, images, fonts, and route latency based on real user conditions. An island can still ship a large framework bundle, and a static page can still be slow because of images or third-party scripts. Measure the whole page instead of assuming “Astro” automatically means fast.
