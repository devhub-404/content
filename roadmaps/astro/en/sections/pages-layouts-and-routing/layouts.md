# Layouts

A layout is an ordinary Astro component used as reusable page structure. It commonly contains the document shell, metadata, navigation, and a slot for page content, but layouts can also be partial wrappers and can be nested.

```astro
---
const { title } = Astro.props;
---
<!doctype html>
<html lang="en">
  <head><title>{title}</title></head>
  <body>
    <SiteHeader />
    <main><slot /></main>
  </body>
</html>
```

Keep layout responsibilities broad and stable, such as site chrome or article framing. Page-specific data should stay in the page unless several routes genuinely share it. Because a layout is a component rather than a special runtime object, it can receive typed props and compose other Astro or framework components normally.
