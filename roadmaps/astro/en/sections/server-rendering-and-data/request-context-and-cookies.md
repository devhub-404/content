# Request Context, Cookies, and Redirects

During on-demand rendering, the `Astro` global exposes request-specific data such as URL, cookies, params, client address where supported, redirects, and response controls. These values belong to one request and should drive request-specific rendering directly.

```astro
---
const session = Astro.cookies.get("session");

if (!session) {
  return Astro.redirect("/login");
}

const url = Astro.url;
---
<p>Path: {url.pathname}</p>
```

Cookies and headers are security boundaries. Set appropriate attributes, validate session data server-side, and avoid leaking secrets into rendered HTML or hydrated props. Static prerendering does not have a live visitor request, so request-dependent APIs require the appropriate runtime rendering mode.
