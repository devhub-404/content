# Forms y Progressive Enhancement

Astro funciona naturalmente con forms HTML estándar. Native submission/validation/navigation ofrecen un baseline completo, mientras Actions/endpoints procesan en server y scripts pueden mejorar feedback progresivamente.

```astro
<form method="POST">
  <label>
    Email
    <input name="email" type="email" required />
  </label>
  <button>Subscribe</button>
</form>
```

Empieza por fields semánticos, labels, button types y server validation. No exijas JavaScript solo para un submit básico salvo necesidad real. Progressive enhancement mantiene forms útiles en redes lentas y reduce states client-side.
