# Scripts Client-side

Un `<script>` normal en un Astro component añade comportamiento en browser sin un UI framework. Astro procesa module scripts mediante el build, deduplica scripts bundled y permite imports client-side.

```astro
<button id="copy">Copy</button>

<script>
  document.querySelector("#copy")?.addEventListener("click", async () => {
    await navigator.clipboard.writeText(location.href);
  });
</script>
```

Usa JavaScript del browser para interacciones pequeñas cuando un framework runtime sería peso innecesario. Asegura comportamiento con varias instancias/navigation. Los inline scripts salen de parte del processing, así que úsalos solo cuando esa forma exacta sea necesaria.
