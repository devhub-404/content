# Forms e Progressive Enhancement

Astro funciona naturalmente com forms HTML padrão. Native submission/validation/navigation oferecem baseline completo, enquanto Actions/endpoints processam no server e scripts podem melhorar feedback progressivamente.

```astro
<form method="POST">
  <label>
    Email
    <input name="email" type="email" required />
  </label>
  <button>Subscribe</button>
</form>
```

Comece por fields semânticos, labels, button types e server validation. Não exija JavaScript só para submit básico salvo necessidade real. Progressive enhancement mantém forms úteis em networks lentas e reduz states client-side.
