# Sessions

Sessions server do Astro fornecem state associado à request com storage configurado. Servem a authenticated state, carts, multi-step workflows e dados persistentes entre requests sem expor tudo ao browser.

```astro
---
const cart = await Astro.session?.get("cart") ?? [];
await Astro.session?.set("cart", [...cart, "book"]);
---
<p>{cart.length} items</p>
```

Armazene só o necessário e entenda lifetime/consistency/deployment do backing store. Session identity não é authorization. Proteja operações no server, invalide credentials quando necessário e evite objects grandes arbitrários por session.
