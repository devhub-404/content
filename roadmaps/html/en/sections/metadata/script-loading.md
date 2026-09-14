# Loading Scripts

A classic script without loading attributes can pause HTML parsing while it downloads and executes. `defer` lets parsing continue and runs deferred scripts after the document has been parsed, in document order. That is usually a better default for application scripts placed in `head`.

```html
<script src="/scripts/app.js" defer></script>
<script type="module" src="/scripts/main.js"></script>
```

Module scripts use `type="module"` and are deferred by default. They support JavaScript imports and exports. `async` is for independent scripts that may run as soon as they are ready; execution order is not preserved between async scripts. Choose the loading mode from the script's dependencies instead of adding `async` or `defer` mechanically.
