---
locale: es
status: published
title: "Next.js"
slug: nextjs
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de Next.js."
tags:
  - nextjs
  - cheatsheet
  - quick-reference
references:
  - label: "React use"
    url: https://react.dev/reference/react/use
  - label: "React Server Functions"
    url: https://react.dev/reference/rsc/server-functions
  - label: "React useActionState"
    url: https://react.dev/reference/react/useActionState
---

# Next.js

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Framework y App Router

**Qué es Next.js**

```tsx
export default function Page() {
  return <h1>Hello Next.js</h1>;
}
```

**Instalación y Estructura de Proyecto**

```tsx
app/
  layout.tsx
  page.tsx
  globals.css
public/
next.config.ts
package.json
tsconfig.json
```

**Next Config y Runtime Choices**

```tsx
import type { NextConfig } from "next";

const nextConfig: NextConfig = {
  reactStrictMode: true,
  cacheComponents: true
};

export default nextConfig;
```

**App Router y Pages Router Legado**

```tsx
// Modern route
// app/dashboard/page.tsx
export default function DashboardPage() {
  return <Dashboard />;
}
```

## Route Tree y Navigation

**Pages y Layouts**

```tsx
// app/dashboard/layout.tsx
export default function Layout({ children }) {
  return (
    <section>
      <DashboardNav />
      <main>{children}</main>
    </section>
  );
}

// app/dashboard/page.tsx
export default function Page() {
  return <h1>Dashboard</h1>;
}
```

**Dynamic Segments y Params**

```tsx
// app/products/[id]/page.tsx
export default async function Page({ params }) {
  const { id } = await params;
  const product = await getProduct(id);
  return <h1>{product.name}</h1>;
}
```

**Route Groups y Private Folders**

```tsx
app/
  (marketing)/
    about/page.tsx
    pricing/page.tsx
  (app)/
    dashboard/page.tsx
  _components/
    Logo.tsx
```

**Parallel e Intercepting Routes**

```tsx
app/
  @modal/
    (.)photo/[id]/page.tsx
  photo/[id]/page.tsx
  layout.tsx
```

**Links, Prefetching y Navigation**

```tsx
import Link from "next/link";

<Link href="/dashboard">Dashboard</Link>
```

## Server y Client Components

**Server Components por Default**

```tsx
export default async function Page() {
  const products = await db.product.findMany();

  return (
    <ul>
      {products.map(product => <li key={product.id}>{product.name}</li>)}
    </ul>
  );
}
```

**Boundaries con `use client`**

```tsx
"use client";

import { useState } from "react";

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```

**Composition entre Server/Client Boundaries**

```tsx
// Server Component
export default function Page() {
  return (
    <ClientModal>
      <ServerProductDetails />
    </ClientModal>
  );
}
```

**Context y Providers**

```tsx
"use client";

export function ThemeProvider({ children }) {
  return <ThemeContext value="dark">{children}</ThemeContext>;
}

// Server layout can render the client provider around children.
```

**Third-party Client Components**

```tsx
"use client";

export { Carousel } from "acme-carousel";
```

## Data Fetching y Streaming

**Fetch en Server Components**

```tsx
export default async function Page() {
  const response = await fetch(process.env.PRODUCTS_API!);
  const products = await response.json();

  return <ProductList products={products} />;
}
```

**Data Fetching Paralelo y Secuencial**

```tsx
const userPromise = getUser(id);
const postsPromise = getPosts(id);

const [user, posts] = await Promise.all([
  userPromise,
  postsPromise
]);
```

**`loading.js` y Suspense Streaming**

```tsx
// app/dashboard/loading.tsx
export default function Loading() {
  return <DashboardSkeleton />;
}

// Fine-grained boundary inside a page
<Suspense fallback={<ChartSkeleton />}>
  <RevenueChart />
</Suspense>
```

**Client Data y React `use`**

```tsx
// Server Component
const commentsPromise = getComments(postId);
return <Comments commentsPromise={commentsPromise} />;

// Client Component
"use client";
function Comments({ commentsPromise }) {
  const comments = use(commentsPromise);
  return comments.map(c => <p key={c.id}>{c.body}</p>);
}
```

**Dynamic APIs y Datos Request-time**

```tsx
import { cookies } from "next/headers";

export default async function Page() {
  const cookieStore = await cookies();
  const theme = cookieStore.get("theme")?.value ?? "light";
  return <main data-theme={theme}>...</main>;
}
```

## Cache Components y Revalidation

**Modelo de Cache Components**

```tsx
// next.config.ts
export default {
  cacheComponents: true
};

export default async function Page() {
  return <ProductPage />;
}
```

**Directive `use cache`**

```tsx
import { cacheLife, cacheTag } from "next/cache";

export async function getProducts() {
  "use cache";
  cacheLife("hours");
  cacheTag("products");
  return db.product.findMany();
}
```

**`cacheLife` y `cacheTag`**

```tsx
import { cacheLife, cacheTag } from "next/cache";

async function getPost(slug) {
  "use cache";
  cacheLife("hours");
  cacheTag("posts", `post:${slug}`);
  return db.post.findUnique({ where: { slug } });
}
```

**`revalidateTag`, `updateTag` y `revalidatePath`**

```tsx
"use server";

import { revalidateTag } from "next/cache";

export async function publishPost() {
  await db.post.publish();
  revalidateTag("posts", "max");
}
```

**Seguridad de Cache y Personalización**

```tsx
async function getPublicCatalog() {
  "use cache";
  return db.product.findMany({ where: { public: true } });
}

async function getCurrentUser() {
  const session = await verifySession();
  return db.user.findUnique({ where: { id: session.userId } });
}
```

## Mutations y Server Functions

**Server Functions y Server Actions**

```tsx
// app/actions.ts
"use server";

export async function createTodo(formData: FormData) {
  const title = String(formData.get("title"));
  await db.todo.create({ data: { title } });
}
```

**Forms con Server Actions**

```tsx
<form action={createTodo}>
  <label>
    Title
    <input name="title" required />
  </label>
  <button>Add todo</button>
</form>
```

**Action State y Optimistic UI**

```tsx
"use client";

const [state, action, pending] = useActionState(saveProfile, { error: null });
const [optimisticName, setOptimisticName] = useOptimistic(name);
```

**Redirect y Revalidation después de Mutations**

```tsx
"use server";

export async function createPost(formData: FormData) {
  const post = await savePost(formData);
  revalidatePath("/posts");
  redirect(`/posts/${post.slug}`);
}
```

**Seguridad de Server Actions**

```tsx
"use server";

export async function deleteProject(projectId: string) {
  const session = await verifySession();
  const project = await db.project.findUnique({ where: { id: projectId } });

  if (!project || project.ownerId !== session.userId) {
    throw new Error("Not authorized");
  }

  await db.project.delete({ where: { id: projectId } });
}
```

## Route Handlers y Request Boundaries

**Route Handlers**

```tsx
// app/api/health/route.ts
export async function GET() {
  return Response.json({ ok: true });
}

export async function POST(request: Request) {
  const body = await request.json();
  return Response.json({ received: body }, { status: 201 });
}
```

**Cookies, Headers y Responses**

```tsx
import { cookies } from "next/headers";

export async function POST() {
  const store = await cookies();
  store.set("theme", "dark", {
    httpOnly: true,
    sameSite: "lax",
    secure: true
  });
  return new Response(null, { status: 204 });
}
```

**Proxy**

```tsx
// proxy.ts
import { NextResponse } from "next/server";

export function proxy(request: Request) {
  const url = new URL(request.url);
  if (url.pathname === "/old") {
    return NextResponse.redirect(new URL("/new", request.url));
  }
  return NextResponse.next();
}
```

**Next.js como Backend for Frontend**

```tsx
// Server-side adapter around an external backend
export async function getAccount() {
  const session = await verifySession();
  return externalApi.get(`/accounts/${session.accountId}`);
}
```

## Metadata y Optimización de Assets

**Metadata API**

```tsx
export const metadata = {
  title: "Store",
  description: "Products and offers"
};

export default function Page() {
  return <h1>Store</h1>;
}
```

**`next/image`**

```tsx
import Image from "next/image";
import hero from "./hero.jpg";

<Image
  src={hero}
  alt="Mountain sunrise"
  sizes="(max-width: 768px) 100vw, 50vw"
  priority
/>
```

**`next/font`**

```tsx
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

export default function RootLayout({ children }) {
  return <html className={inter.className}><body>{children}</body></html>;
}
```

**Scripts y Código Third-party**

```tsx
import Script from "next/script";

<Script
  src={process.env.NEXT_PUBLIC_WIDGET_SRC!}
  strategy="lazyOnload"
/>
```

## Errors, Auth y Seguridad

**Error y Not-found Boundaries**

```tsx
// app/dashboard/error.tsx
"use client";

export default function Error({ error, reset }) {
  return (
    <div>
      <p>Could not load the dashboard.</p>
      <button onClick={reset}>Try again</button>
    </div>
  );
}
```

**Authentication, Sessions y Authorization**

```tsx
export async function verifySession() {
  const session = await readSessionCookie();
  if (!session) redirect("/login");
  return session;
}

export async function getProject(id: string) {
  const session = await verifySession();
  return db.project.findFirst({ where: { id, ownerId: session.userId } });
}
```

**Código Server-only y Environment Variables**

```tsx
import "server-only";

export async function getBillingData() {
  const secret = process.env.BILLING_SECRET;
  return billingClient(secret).read();
}
```

**Content Security Policy**

```tsx
// Example response header
const nonce = createNonce();

return new NextResponse(response.body, {
  headers: {
    "Content-Security-Policy": `script-src 'self' 'nonce-${nonce}'`
  }
});
```

**Validación de Datos y Serialization Segura**

```tsx
const input = CreateUserSchema.parse({
  email: formData.get("email"),
  name: formData.get("name")
});

const userView = {
  id: user.id,
  name: user.name
};
```

## Testing, Observability y Performance

**Estrategia de Testing**

```tsx
await page.goto("/dashboard");
await expect(page.getByRole("heading", { name: "Dashboard" })).toBeVisible();
await page.getByRole("button", { name: "Create project" }).click();
```

**Instrumentation y Logging**

```tsx
// instrumentation.ts
export async function register() {
  if (process.env.NEXT_RUNTIME === "nodejs") {
    await import("./instrumentation-node");
  }
}
```

**Bundle Size y Client Boundaries**

```tsx
// Keep heavy server-only dependencies out of client modules.
import "server-only";
import { expensivePdfLibrary } from "pdf-library";

export async function createInvoicePdf() {
  return expensivePdfLibrary.render(...);
}
```

**Core Web Vitals y Navigation Performance**

```tsx
import { useReportWebVitals } from "next/web-vitals";

export function WebVitals() {
  useReportWebVitals(metric => {
    sendToAnalytics(metric);
  });
  return null;
}
```

## Deployment y Upgrades

**Modelos de Deployment**

```tsx
# Standard production build
npm run build
npm run start

# Or use a supported platform adapter/deployment integration.
```

**Static Export**

```tsx
// next.config.ts
export default {
  output: "export"
};
```

**Adapters y Portabilidad de Plataforma**

```tsx
// Platform adapters translate the Next.js build/runtime
// contract to a target host. Keep application code within
// APIs supported by every platform you promise to run on.
```
