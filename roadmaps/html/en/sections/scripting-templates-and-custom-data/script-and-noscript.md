# `script` and `noscript`

`script` embeds or loads JavaScript. Prefer external files for reusable application code and choose classic, deferred, async, or module loading based on dependencies. Inline scripts are valid but can make caching, security policy, and maintenance harder when they grow beyond document-specific setup.

```html
<script type="module" src="/scripts/main.js"></script>

<noscript>
  <p>This dashboard needs JavaScript for live editing.</p>
</noscript>
```

`noscript` provides markup for environments where relevant scripting is disabled or unavailable. Use it when the no-script experience needs a real explanation or alternative path. Better still, when the product allows it, render useful content and forms in HTML first and enhance them with JavaScript rather than making the entire document blank without script execution.
