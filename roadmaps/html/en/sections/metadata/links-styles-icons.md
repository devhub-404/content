# Stylesheets, Icons, and Resource Links

The `link` element describes a relationship between the current document and another resource. `rel="stylesheet"` loads CSS, while `rel="icon"` supplies an icon for browser or installed-site UI. `link` normally belongs in `head` because it describes the document rather than visible body content.

```html
<link rel="stylesheet" href="/styles/site.css">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="preload" href="/fonts/ui.woff2" as="font" type="font/woff2" crossorigin>
```

Resource hints such as `preload` can tell the browser that an important resource will be needed soon. They are performance tools, not boilerplate. Incorrect or excessive preloads can compete with resources the browser would otherwise prioritize well. Add hints only for resources whose early fetch has a measured benefit.
