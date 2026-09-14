# Forms and Progressive Enhancement

Astro works naturally with standard HTML forms. Native form submission, validation, and navigation can provide a complete baseline experience, while Actions or endpoint handlers add server processing and client scripts can progressively enhance feedback when needed.

```astro
<form method="POST">
  <label>
    Email
    <input name="email" type="email" required />
  </label>
  <button>Subscribe</button>
</form>
```

Start from semantic fields, labels, button types, and server validation. Do not require client JavaScript simply to submit basic data unless the product truly needs a richer interaction. Progressive enhancement keeps forms usable on slow networks and reduces the number of states the client must own.
