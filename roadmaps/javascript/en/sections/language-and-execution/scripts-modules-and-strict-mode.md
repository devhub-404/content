# Scripts, Modules, and Strict Mode

Browser JavaScript can run as a classic script or as an ECMAScript module. Modules have their own top-level scope, support `import` and `export`, allow top-level `await`, and are strict by default. Classic scripts have older global-scope and loading behavior and can opt into strict mode with `"use strict"`.

```html
<script src="/legacy.js" defer></script>
<script type="module" src="/app.js"></script>
```

Modern application code usually benefits from modules because dependencies are explicit and names stay local unless exported. Strict mode removes several error-prone legacy behaviors and turns some silent mistakes into errors. Module resolution is host-defined: browsers primarily resolve URLs, while server runtimes and build tools can add package-resolution rules.
