# Client-side Scripts

A normal `<script>` in an Astro component can add browser behavior without introducing a UI framework. Astro processes module scripts through the build pipeline, deduplicates bundled scripts, and lets them import other client-side modules.

```astro
<button id="copy">Copy</button>

<script>
  document.querySelector("#copy")?.addEventListener("click", async () => {
    await navigator.clipboard.writeText(location.href);
  });
</script>
```

Use plain browser JavaScript for small interactions when component state or a framework runtime would add unnecessary weight. Keep scripts resilient to navigation behavior and repeated component instances. Inline scripts opt out of some Astro processing, so use them only when that exact execution form is required.
