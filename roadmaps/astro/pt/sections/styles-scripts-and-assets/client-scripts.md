# Scripts Client-side

Um `<script>` normal em Astro component adiciona comportamento no browser sem UI framework. Astro processa module scripts pelo build, deduplica scripts bundled e permite imports client-side.

```astro
<button id="copy">Copy</button>

<script>
  document.querySelector("#copy")?.addEventListener("click", async () => {
    await navigator.clipboard.writeText(location.href);
  });
</script>
```

Use JavaScript do browser para interações pequenas quando framework runtime seria peso desnecessário. Garanta comportamento com múltiplas instâncias/navigation. Inline scripts saem de parte do processing, então use apenas quando forma exata é necessária.
