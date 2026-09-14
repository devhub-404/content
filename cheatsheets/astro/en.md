---
locale: en
status: published
title: "Astro"
slug: astro
description: "A task-oriented quick reference for everyday Astro syntax, APIs, and workflows."
tags:
  - astro
  - cheatsheet
  - quick-reference
references:
  - label: "MDN: Forms"
    url: https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms
  - label: "Astro: Why Astro?"
    url: https://docs.astro.build/en/concepts/why-astro/
  - label: "Astro Docs"
    url: https://docs.astro.build/en/basics/project-structure/
---

# Astro

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Astro Model & Project

**Project Structure**

```astro
src/
  components/
  layouts/
  pages/
  styles/
  content.config.ts
public/
astro.config.mjs
package.json
```

**Astro Config and Integrations**

```astro
import { defineConfig } from "astro/config";
import react from "@astrojs/react";

export default defineConfig({
  integrations: [react()],
  output: "static"
});
```

**Development, Build, and Preview**

```astro
{
  "scripts": {
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview",
    "check": "astro check"
  }
}
```

## Astro Components

**Component Structure and Frontmatter**

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

**Props and TypeScript**

```astro
---
interface Props {
  title: string;
  featured?: boolean;
}

const { title, featured = false } = Astro.props;
---

<article class:list={{ featured }}>
  <h2>{title}</h2>
</article>
```

**Slots and Component Composition**

```astro
<!-- Card.astro -->
<article class="card">
  <header><slot name="header" /></header>
  <div><slot /></div>
</article>

<!-- usage -->
<Card>
  <h2 slot="header">Profile</h2>
  <p>Account details</p>
</Card>
```

**Template Expressions and Directives**

```astro
---
const items = ["HTML", "CSS", "JS"];
const active = true;
---

<ul class:list={["topics", { active }]}>
  {items.map(item => <li>{item}</li>)}
</ul>
```

## Pages, Layouts & Routing

**File-based Pages**

```astro
// src/pages/about.astro -> /about
---
const title = "About";
---
<html>
  <head><title>{title}</title></head>
  <body><h1>{title}</h1></body>
</html>
```

**Layouts**

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

**Dynamic Routes and `getStaticPaths`**

```astro
---
export function getStaticPaths() {
  return [
    { params: { slug: "hello" }, props: { title: "Hello" } },
    { params: { slug: "astro" }, props: { title: "Astro" } }
  ];
}

const { slug } = Astro.params;
const { title } = Astro.props;
---
<h1>{title}</h1>
<p>{slug}</p>
```

**Routing Priority and Advanced Routing**

```astro
// Conventional routes live in src/pages/.
// Astro 7 also supports advanced request-pipeline routing
// for projects that deliberately need lower-level control.
```

## Styles, Scripts & Assets

**Scoped and Global Styles**

```astro
<style>
  h2 { color: rebeccapurple; }
</style>

<style is:global>
  :root { font-family: system-ui, sans-serif; }
</style>

<h2>Scoped heading</h2>
```

**Client-side Scripts**

```astro
<button id="copy">Copy</button>

<script>
  document.querySelector("#copy")?.addEventListener("click", async () => {
    await navigator.clipboard.writeText(location.href);
  });
</script>
```

**Images and Image Optimization**

```astro
---
import { Image } from "astro:assets";
import hero from "../assets/hero.jpg";
---

<Image src={hero} alt="Mountain at sunrise" width={1200} />
```

**Fonts**

```astro
---
import { Font } from "astro:assets";
---

<Font cssVariable="--font-brand" />
<style>
  h1 { font-family: var(--font-brand), sans-serif; }
</style>
```

## Islands & UI Frameworks

**Islands Architecture**

```astro
---
import Counter from "../components/Counter.jsx";
---

<h1>Mostly static page</h1>
<Counter client:visible />
```

**Client Hydration Directives**

```astro
<NavMenu client:load />
<Chart client:visible />
<Search client:idle />
<ThemePicker client:media="(max-width: 48rem)" />
```

**Using React, Vue, Solid, and Other Framework Components**

```astro
---
import ReactCard from "../components/ReactCard.jsx";
import SolidCounter from "../components/SolidCounter.tsx";
---

<ReactCard title="Static render" />
<SolidCounter client:visible />
```

**Server Islands**

```astro
---
import PersonalizedAvatar from "../components/PersonalizedAvatar.astro";
---

<PersonalizedAvatar server:defer>
  <div slot="fallback" class="avatar-placeholder"></div>
</PersonalizedAvatar>
```

## Content & Markdown

**Markdown and MDX**

```astro
---
title: "Learning Astro"
published: 2026-09-12
---

# {frontmatter.title}

Astro can render **Markdown** content.
```

**Content Collections**

```astro
// src/content.config.ts
import { defineCollection, z } from "astro:content";

const blog = defineCollection({
  schema: z.object({
    title: z.string(),
    published: z.date()
  })
});

export const collections = { blog };
```

**Content Loaders and Live Content**

```astro
const products = defineCollection({
  loader: customApiLoader({ endpoint: process.env.PRODUCTS_URL }),
  schema: productSchema
});
```

**Rendering Collection Entries**

```astro
---
import { getCollection, render } from "astro:content";

const posts = await getCollection("blog");
const post = posts[0];
const { Content } = await render(post);
---

<article>
  <h1>{post.data.title}</h1>
  <Content />
</article>
```

## Server Rendering & Data

**Static vs On-demand Rendering**

```astro
import { defineConfig } from "astro/config";
import node from "@astrojs/node";

export default defineConfig({
  output: "server",
  adapter: node({ mode: "standalone" })
});
```

**Request Context, Cookies, and Redirects**

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

**Endpoints and API Routes**

```astro
// src/pages/api/status.ts
export function GET() {
  return Response.json({ ok: true });
}

export async function POST({ request }) {
  const body = await request.json();
  return Response.json({ received: body });
}
```

**Middleware**

```astro
import { defineMiddleware } from "astro:middleware";

export const onRequest = defineMiddleware(async (context, next) => {
  context.locals.requestId = crypto.randomUUID();
  const response = await next();
  response.headers.set("x-request-id", context.locals.requestId);
  return response;
});
```

## Actions, Sessions & Forms

**Astro Actions**

```astro
// src/actions/index.ts
import { defineAction } from "astro:actions";
import { z } from "astro:schema";

export const server = {
  createTodo: defineAction({
    input: z.object({ title: z.string().min(1) }),
    handler: async ({ title }) => db.todos.create({ title })
  })
};
```

**Forms and Progressive Enhancement**

```astro
<form method="POST">
  <label>
    Email
    <input name="email" type="email" required />
  </label>
  <button>Subscribe</button>
</form>
```

**Sessions**

```astro
---
const cart = await Astro.session?.get("cart") ?? [];
await Astro.session?.set("cart", [...cart, "book"]);
---
<p>{cart.length} items</p>
```

**CSRF and Request Security**

```astro
export default defineConfig({
  security: {
    checkOrigin: true
  }
});
```

## Navigation, Performance & Security

**View Transitions and Client Router**

```astro
---
import { ClientRouter } from "astro:transitions";
---
<head>
  <ClientRouter />
</head>

<h1 transition:name="page-title">Docs</h1>
```

**Route Caching**

```astro
// Configure caching only for routes whose response semantics allow it.
export const prerender = false;

Astro.response.headers.set(
  "Cache-Control",
  "public, max-age=60, s-maxage=600"
);
```

**Content Security Policy**

```astro
export default defineConfig({
  security: {
    csp: {
      directives: {
        "default-src": ["'self'"]
      }
    }
  }
});
```

**Performance Budgets and Zero-JS Defaults**

```astro
---
import ProductGrid from "../components/ProductGrid.astro";
import CartButton from "../components/CartButton.jsx";
---

<ProductGrid products={products} />
<CartButton client:load />
```

## Testing, Deployment & Upgrades

**Testing Strategy**

```astro
// End-to-end example
await page.goto("/docs");
await expect(page.getByRole("heading", { name: "Docs" })).toBeVisible();
await page.getByRole("link", { name: "Getting started" }).click();
```

**Adapters and Deployment**

```astro
import { defineConfig } from "astro/config";
import cloudflare from "@astrojs/cloudflare";

export default defineConfig({
  output: "server",
  adapter: cloudflare()
});
```

**Environment Variables and Secrets**

```astro
const publicApi = import.meta.env.PUBLIC_API_BASE;
const privateKey = import.meta.env.SECRET_API_KEY;
```
