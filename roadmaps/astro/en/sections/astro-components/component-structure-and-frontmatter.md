# Component Structure and Frontmatter

An `.astro` component has a server-side component script between `---` fences and a template below it. Imports, data loading, and calculations in frontmatter run while Astro renders the component; that JavaScript is not automatically sent to the browser.

```astro
---
import Avatar from "./Avatar.astro";
const { name } = Astro.props;
const greeting = `Hello, ${name}`;
---

<section>
  <Avatar name={name} />
  <p>{greeting}</p>
</section>
```

Use frontmatter to prepare data and the template to describe output. Because frontmatter is server/build code, it can access server-only dependencies when the rendering mode permits it. Do not place browser-only APIs there unless the code is explicitly moved into a client script or hydrated island.
