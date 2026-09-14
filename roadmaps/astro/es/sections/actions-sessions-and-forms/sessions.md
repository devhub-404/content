# Sessions

Las sessions server de Astro ofrecen state asociado a la request con storage configurado. Sirven para authenticated state, carts, multi-step workflows y datos persistentes entre requests sin exponer todo al browser.

```astro
---
const cart = await Astro.session?.get("cart") ?? [];
await Astro.session?.set("cart", [...cart, "book"]);
---
<p>{cart.length} items</p>
```

Guarda solo lo necesario y entiende lifetime/consistency/deployment del backing store. Session identity no es authorization. Protege operaciones en server, invalida credentials cuando corresponda y evita objects grandes arbitrarios por session.
