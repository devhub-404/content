# Sessions

Astro's server session facilities provide request-associated state backed by a configured session storage implementation. Sessions are useful for authenticated state, carts, multi-step workflows, and other data that should persist across requests without being exposed entirely to the browser.

```astro
---
const cart = await Astro.session?.get("cart") ?? [];
await Astro.session?.set("cart", [...cart, "book"]);
---
<p>{cart.length} items</p>
```

Store only what the application actually needs and understand the backing store's lifetime, consistency, and deployment requirements. Session identity is not authorization by itself. Protect sensitive operations on the server, rotate or invalidate credentials appropriately, and avoid storing large arbitrary objects in every session.
